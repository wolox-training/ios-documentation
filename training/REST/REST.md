## Requests con Alamofire

Comencemos creando un Repository, que vamos a utilizar para realizar todas nuestras requests. Para esto creamos la siguiente clase:

```Swift
import Result
import Alamofire

public class BookRepository {

}
```

Luego creamos la función para traer los libros. Esta función va a recibir 2 parámetros:

```Swift
onSuccess: ([Book]) -> Void
```

Esta función recibe una lista de libros y se va a ejecutar cuando obtengamos una respuesta válida a nuestro pedido.

```Swift
onError: (Error) -> Void
```

Esta función recibe un error, y es justamente la función que queremos que se ejecute en caso de que algo falle al realizar el pedido.
 
Entonces creamos la siguiente función:

```Swift
public func fetchBooks(onSuccess: @escaping ([Entity]) -> Void, onError: @escaping (Error) -> Void) {

}
```

Luego tenemos que armar la url a la que queremos hacer la request, la url es `https://ios-training-backend.herokuapp.com/api/v1`y en Swift la podemos armar de la siguiente manera:

```Swift 
let url = URL(string: "https://ios-training-backend.herokuapp.com/api/v1/books")!
```


Una vez que tenemos la url ejecutamos la request con el método GET:

```Swift
request(url, method: .get).responseJSON(completionHandler: { _ in} )
```

Esta función ya está ejecutando el pedido de los libros, pero aún nos falta manejar la respuesta del pedido, ya sea la lista de los libros o un error. Como podemos ver, `responseJSON` recibe como parámetro una función `completionHandler` (de tipo `(DataResponse<Any>) -> Void)`. Ahí es donde vamos a manejar la respuesta que recibimos de la request.
 
Primero comenzamos por ver si la respuesta fue correcta o si recibimos un error, para lo cual haremos lo siguiente:

```Swift
request(url, method: .get).responseJSON // Handle response { response in //check if request was succesful     switch response.result {     case .success(let value):     // request was successful
         (Handle value...)     case .failure(let error):     // request failed so we call the error function         onError(error)     } }
```

Aquí hacemos un switch de `response.result`. Este valor es un enum que puede ser .success o .failure. Si es success, tiene un valor asociado con los datos de los libros; si es failure tiene asociado un Error. Como vemos, si la respuesta es un error llamamos directamente a la función onError con el error que recibimos. Solo nos falta manejar los datos recibidos en caso de que la respuesta sea exitosa.

El objetivo es transformar la respuesta del servidor que nos viene en formato JSON a un array de nuestro modelo Book. Para esto podemos utilizar el protocolo Codable que nos brinda Apple. Entonces vayamos a nuestra clase Book y hagamos que conforme al protocolo Codable:

```Swift
public struct Book: Codable {     let id: Int     let title: String     let author: String     let genre: String     let year: String     let image: String }
```
 
Para poder transformar los datos necesitamos crear el constructor init(from: Decoder). Para esto lo más conveniente es crear un enumerable con todas las claves del JSON de esta forma:   ```Swift
enum BookKey: String, CodingKey {     case id = "id"     case title = "title"     case author = "author"     case genre = "genre"     case year = "year"     case image = "image" }
```

Y luego implementamos init(from: Decoder):

```Swift
public init(from: Decoder) {
    let container = try! from.container(keyedBy: BookKey.self)
    id = try! container.decode(Int.self, forKey: .id)
    title = try! container.decode(String.self, forKey: .title)
    author = try! container.decode(String.self, forKey: .author)
    genre = try! container.decode(String.self, forKey: .genre)
    year = try! container.decode(String.self, forKey: .year)
    image = try! container.decode(String.self, forKey: .image)
}
```
 
Aclaración: tal vez te hayas dado cuenta que cuando le agregamos la extensión Codable a nuestro modelo no recibimos ningún error de que nuestra estructura no conforma al protocolo. Esto sucede por la misma razón que no necesitamos declarar un init() en los structs, y es que ya hay una función init(from: Decoder) default que se utiliza en caso de que nosotros no definamos la función. Esta función default utiliza como claves los nombres de los atributos de la estructura en string, por lo tanto si los nombres de los atributos de nuestra clase coinciden con las claves del JSON no necesitamos hacer nada de todo esto, solo agregar el protocolo a la estructura.
 
Finalmente terminamos de manejar el valor de respuesta, para esto agregamos debajo del case .success(let value):
 
```Swift
//check if data is valid, if not call error function guard let JSONbooks = try? JSONSerialization.data(withJSONObject: value, options: []) else {[1]      onError(BookError.decodeError)     return } //check if data is valid, if not call error function guard let books = try? JSONDecoder().decode([Book].self, from: JSONbooks) else {     onError(BookError.decodeError)     return } // request was successful and data is valid so we call success function onSuccess(books)
```

En el primer guard nos fijamos si podemos convertir el resultado a Data, en caso de no poder llamamos a la función onError, ya que recibimos datos incorrectos. En el segundo guard nos fijamos si ese Data lo podemos convertir a un array de libros [Book]. En caso de que falle también llamamos a la función de error. Finalmente si logramos transformar los datos llamamos a la función onSuccess con la lista de los libros que recibimos.

Solo nos falta definir el Error que estamos devolviendo cuando falla la conversión de los datos, lo podemos hacer de la siguiente forma:

```Swift
enum BookError: Error {     case decodeError }
```

El código final del repositorio nos queda:

```Swift
import Result
import Alamofire

class BookRepository {

	public func fetchBooks(onSuccess: @escaping ([Book]) -> Void, onError: @escaping (Error) -> Void) {
		let url = URL(string: "https://ios-training-backend.herokuapp.com/api/v1/books")!

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