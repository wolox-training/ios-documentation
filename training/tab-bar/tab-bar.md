Introduccion a Tab bar controllers
 
¿Qué es un Tab bar controller?
 
Es un contenedor para otros ViewControllers, que nos permite agregar tabs para cada uno de los controllers que agreguemos, de esta forma el usuario puede acceder a cualquiera de los controlladores tocando la tab correspondiente. El TabBarController se encarga de manejar la transición entre las pantallas y la selección de las tabs. 
 
Para crear un TabBarController hacemos lo siguiente:
 
-       Vamos a File -> New -> File
            
 
-       Seleccionamos cocoa touch class

 
-       Elegimos el nombre de nuestra clase y en subclass of elegimos UITabBarViewController

 
-       Finalmente le damos create:

Esto nos va a crear el siguiente archivo:
 
import UIKit  class TabBarController: UITabBarController {      override func viewDidLoad() {         super.viewDidLoad()          // Do any additional setup after loading the view.     }           /*     // MARK: - Navigation      // In a storyboard-based application, you will often want to do a little preparation before navigation     override func prepare(for segue: UIStoryboardSegue, sender: Any?) {         // Get the new view controller using segue.destination.         // Pass the selected object to the new view controller.     }     */  }
 
Configuremos esta Tab bar para que tenga 2 tabs, una para “Library” y una para “WishList”. Ten en cuenta que HomeController y WhichListController son ViewControllers
 
Empecemos por borrar los comentarios que vienen con el template:
 
class TabBarController: UITabBarController {      override func viewDidLoad() {         super.viewDidLoad()     } }
 
Primero en viewDidLoad creemos los controllers para cada tab y asignémoslos a nuestro tab bar.
 
class TabBarViewController: UITabBarController {          override func viewDidLoad() {         super.viewDidLoad()                  let home = HomeController()         let wishList = WishListController()                  viewControllers = [home, wishList]     }      }
 
Ahora tenemos que configurar la imagen y el titulo de cada tab, para esto le creamos un TabBarItem a cada controller:
 
class TabBarViewController: UITabBarController {          override func viewDidLoad() {         super.viewDidLoad()                  let home = HomeController()         home.tabBarItem = UITabBarItem()         home.tabBarItem.title = title         home.tabBarItem.image = UIImage(named: "home.png")         home.tabBarItem.tag = 0                  let wishList = WishListController()         wishList.tabBarItem = UITabBarItem()         wishList.tabBarItem.title = title         wishList.tabBarItem.image = UIImage(named: "wishlist.png")         wishList.tabBarItem.tag = 1                  viewControllers = [home, wishList]     }      }

El atributo tag es un identificador que le damos a cada tab para poder identificarla.
 
Podemos configurar también la apariencia de la tab bar, por ejemplo podemos setear el color de la tab bar a gris de la siguiente forma:


class TabBarViewController: UITabBarController {          override func viewDidLoad() {         super.viewDidLoad()                  // change tab bar color         tabBar.barTintColor = .gray                  let home = HomeController()         home.tabBarItem = UITabBarItem()         home.tabBarItem.title = title         home.tabBarItem.image = UIImage(named: "home.png")         home.tabBarItem.tag = 0                  let wishList = WishListController()         wishList.tabBarItem = UITabBarItem()         wishList.tabBarItem.title = title         wishList.tabBarItem.image = UIImage(named: "wishlist.png")         wishList.tabBarItem.tag = 1                  viewControllers = [home, wishList]     } }