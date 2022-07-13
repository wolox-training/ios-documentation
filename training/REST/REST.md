## Requests con Alamofire

1. Comencemos creando un Repository, la entidad que utilizaremos para realizar nuestras requests:

```Swift
import Result
import Alamofire

class BookRepository {

}
```

2. Luego, creamos la función para traer los libros:

```Swift
onSuccess: ([Book]) -> Void
```

Esta función recibe una lista de libros y se va a ejecutar cuando obtengamos una respuesta válida a nuestro pedido.

3. Agregamos también una función para recibir posibles errores:

```Swift
onError: (Error) -> Void
```

Como dijimos, Eesta función recibe un error, y es justamente la función que queremos que se ejecute en caso de que algo falle al realizar el pedido.
 
4. Creamos la siguiente función:

```Swift
func fetchBooks(onSuccess: @escaping ([Entity]) -> Void, onError: @escaping (Error) -> Void) {

}
```

Luego, tenemos que preparar la URL a la que queremos hacer la request. En este caso es `https://private-deb86-wbooksiostraining.apiary-mock.com/books` y en Swift la podemos preparar de la siguiente manera:

```Swift 
let url = URL(string: "https://private-deb86-wbooksiostraining.apiary-mock.com/books")!
```

5. Una vez que tenemos la URL preparada, ejecutamos la request con el método GET:

```Swift
request(url, method: .get).responseJSON(completionHandler: { _ in} )
```

Esta función hará el pedido de los libros, pero aún nos falta manejar la respuesta del pedido, ya sea la lista de los libros o un error. Como podemos ver, `responseJSON` recibe como parámetro una función `completionHandler` (de tipo `(DataResponse<Any>) -> Void)`. Ahí es donde vamos a manejar la respuesta que recibimos de la request.
 
6. Veamos si la respuesta fue correcta o si recibimos un error, para lo cual haremos lo siguiente:

```Swift
request(url, method: .get).responseJSON { response in

	switch response.result {
	case .success(let value):
		// Request was successful
		// (Handle value...)
	case .failure(let error):
		// Request failed so we call the error function
		onError(error)
	}
}
```

Aquí hacemos un switch de `response.result`. Este valor es un Enum que puede ser `.success` o `.failure`. Si es success, tendrá un valor asociado con los datos de los libros; si es failure tendrá asociado un Error. Como vemos, si la respuesta es un error llamamos directamente a la función `onError` y le pasamos el error que recibimos. 

7. Solo nos falta manejar los datos recibidos en caso de que la respuesta sea exitosa. El objetivo es transformar la respuesta del servidor que nos viene en formato JSON a un array de nuestro modelo Book. Para esto podemos utilizar el protocolo Codable que nos brinda Apple. De modo que vayamos a nuestra clase Book y hagamos que conforme al protocolo Codable:

```Swift
struct Book: Codable {
	let id: Int
	let title: String
	let author: String
	let genre: String
	let year: String
	let image: String
}
```
 
Para poder transformar los datos necesitamos crear el constructor `init(from: Decoder)`. Pero primero, creemos un enumerable con todas las claves del JSON de esta forma:

```Swift
enum BookKey: String, CodingKey {
	case id = "id"
	case title = "title"
	case author = "author"
	case genre = "genre"
	case year = "year"
	case image = "image" }
```

Ahora sí, implementemos nuestro initializer:

```Swift
init(from: Decoder) {
    let container = try! from.container(keyedBy: BookKey.self)
    id = try! container.decode(Int.self, forKey: .id)
    title = try! container.decode(String.self, forKey: .title)
    author = try! container.decode(String.self, forKey: .author)
    genre = try! container.decode(String.self, forKey: .genre)
    year = try! container.decode(String.self, forKey: .year)
    image = try! container.decode(String.self, forKey: .image)
}
```

Aclaración: tal vez te hayas dado cuenta que cuando le agregamos la extensión Codable a nuestro modelo no recibimos ningún error de que nuestra estructura no conforma al protocolo. Esto sucede por la misma razón que no necesitamos declarar un `init()` en los structs, y es que ya hay una función init(from: Decoder) default que se utiliza en caso de que nosotros no definamos la función. Esta función default utiliza como claves los nombres de los atributos de la estructura en string, por lo tanto si los nombres de los atributos de nuestra clase coinciden con las claves del JSON no necesitamos hacer nada de todo esto, solo agregar el protocolo a la estructura.
 
8. Finalmente terminamos de manejar el valor de respuesta, para esto agregamos debajo del case `.success(let value)`:
 
```Swift
//check if data is valid, if not call error function
guard let JSONbooks = try? JSONSerialization.data(withJSONObject: value, options: []) else {
	onError(BookError.decodeError)
	return
}
//check if data is valid, if not call error function
guard let books = try? JSONDecoder().decode([Book].self, from: JSONbooks) else {
	onError(BookError.decodeError)
	return
}

// request was successful and data is valid so we call success function
onSuccess(books)
```

En el primer guard nos fijamos si podemos convertir el resultado a Data, en caso de no poder llamamos a la función onError, ya que recibimos datos incorrectos. En el segundo guard nos fijamos si ese Data lo podemos convertir a un array de libros [Book]. En caso de que falle también llamamos a la función de error. Finalmente si logramos transformar los datos llamamos a la función onSuccess con la lista de los libros que recibimos.

9. Solo nos falta definir el Error que estamos devolviendo cuando falla la conversión de los datos, lo podemos hacer de la siguiente forma:

```Swift
enum BookError: Error {
	case decodeError
}
```

El código final del repositorio nos queda:

```Swift
import Result
import Alamofire

class BookRepository {
	
	func fetchBooks(onSuccess: @escaping ([Book]) -> Void, onError: @escaping (Error) -> Void) {
		let url = URL(string: "https://private-deb86-wbooksiostraining.apiary-mock.com/books")!

		request(url, method: .get).responseJSON { response in

			switch response.result {
			case .success(let value):
				guard let JSONbooks = try? JSONSerialization.data(withJSONObject: value, options: []) else {
				onError(BookError.decodeError)
					return
				}

				guard let books = try? JSONDecoder().decode([Book].self, from: JSONbooks) else {
					onError(BookError.decodeError)
					return
				}

				onSuccess(books)

			case .failure(let error):
				onError(error)
			}
		}
	}
}

enum BookError: Error {
	case decodeError
}
```

Luego para realizar una request por ejemplo hacemos: 
 
```Swift
let onSuccess = { books in
	print(books)
}

let onError = { error in
	print(error)
}

repository.fetchBooks(onSuccess: onSuccess, onError: onError)
```

En este caso estamos imprimiendo los datos o el error que obtengamos de la request, en el caso del training en onSuccess habría que guardar los datos en el ViewModel y recargar la tabla, y en onError mostrar un Alert informando que ocurrió un error.
