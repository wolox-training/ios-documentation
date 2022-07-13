## ¿Que cosas entran en el View Model?

Como el título lo indica, el objetivo de este documento es clarificar qué cosas deben estar contenidas en el View Model y qué cosas deben estar en el View Controller a la hora de utilizar la arquitectura MVVM. 

En el training hay un link a una explicación de MVVM y un ejemplo práctico de cómo refactorizar una aplicación que utiliza MVC a MVVM. La idea es ampliar esta definición con más ejemplos prácticos de casos que pueden aparecer en las aplicaciones.
 
Para empezar, repasemos la definición de View Controller y View Model que nos da el tutorial del training:

>According to the definition, the View consists of only visual elements. In the View, we only do things like layout, animation, initializing UI components, etc. There’s a special layer between the View and the Model called the ViewModel. The ViewModel is a canonical representation of the View. That is, the ViewModel provides a set of interfaces, each of which represents a UI component in the View. We use a technique called “binding” to connect UI components to ViewModel interfaces. So, in MVVM, we don’t touch the View directly, we deal with business logic in the ViewModel and thus the View changes itself accordingly. We write presentational things such as converting Date to String in the ViewModel instead of the View. Therefore, it becomes possible to write a simpler test for the presentational logic without knowing the implementation of the View.

Podemos entender de esto que todo lo que tenga que ver con lógica de negocio tiene que estar contenido en el View Model. De la misma manera, cualquier cosa que represente un estado en la app debe estar contenido también en el viewModel (por ejemplo, el texto que se tiene que mostrar en una label, la fecha que selecciono el usuario, el estado de un botón habilitado/deshabilitado, los elementos que tiene una tabla, etc.). También todo lo que tenga que ver con búsqueda de datos (obtener los modelos), se tiene que realizar en el View Model, ya sea requests a un servidor o almacenamiento en la base de datos local del teléfono.

Entonces, ¿qué cosas quedan en el View/ViewController? En principio todo lo que tenga que ver con actualizar la UI de la aplicación, es decir, mostrar los datos que nos está dando el View Model (siguiendo los ejemplos anteriores: asignar el texto a una label, mostrar la fecha que selecciono el usuario en un label, cambiar el color de un botón según su estado habilitado/deshabilitado, mostrar los elementos de la tabla). También todo lo que tenga que ver con capturar los inputs del usuario, por ejemplo obtener el texto que escribe el usuario en un Text Field (cabe aclarar que esto solo incluye capturar el input, el valor obtenido de un textfield se pasa inmediatamente al View Model, ya que representa lógica de negocio). También se incluye en el View Controller todo lo que tenga que ver con navegación de la app y presentación de alerts/modals.

Para mayor detalle, presentamos una planilla con más ejemplos:

| View/ViewController | ViewModel |
| --- | ----------- |
| Actualización de UI (y bindings en caso de reactive)  | Requests de datos (networking)|
| Delegate de tablas/collections| Búsqueda de datos almacenados localmente |
| Reload de las tablas/collections | Manejo del estado de la app (¿está cargando?, ¿debe mostrar el botón de aceptar?, ¿la tabla está vacía?, etc) |
| Captura de inputs del usuario | Lógica de negocio (¿el usuario ingresó un log nuevo, tengo  que crear uno nuevo o tengo que reemplazar uno existente?) |
| Setup de la navigationBar | Datos de presentación y formato (todo lo que tiene que mostrar la vista que no sea estático). |
| Presentacion de alerts/modals |  |
| Navegacion entre pantallas |  |
| Setup de Tab Bar |  |