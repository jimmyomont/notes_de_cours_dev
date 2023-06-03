# UIKIT

## 1 - Principes de base de l'UIKit :
Importer le framework UIKit 

Créez une nouvelle UIWindow 

Définissez le contrôleur de vue racine 

Rendre la fenêtre visible 

```swift 
import UIKit

let window = UIWindow(frame: UIScreen.main.bounds)
let viewController = UIViewController() // Replace with your own view controller
window.rootViewController = viewController
window.makeKeyAndVisible()
```

## 2 - Vue UI :
Créez une nouvelle vue 

Ajouter une sous-vue 

Définir la couleur d'arrière-plan 

Définir le rayon d'angle

Définissez la largeur et la couleur de la bordure 

```swift 
let view = UIView(frame: CGRect(x: 0, y: 0, width: 100, height: 100))
view.backgroundColor = UIColor.red
view.layer.cornerRadius = 10
view.layer.borderWidth = 1
view.layer.borderColor = UIColor.black.cgColor

parentView.addSubview(view)
```
## 3 - ÉtiquetteUI :
Créez une nouvelle étiquette

Définir le texte

Définir la police 

Définir la couleur du texte

```swift 
let label = UILabel(frame: CGRect(x: 0, y: 0, width: 200, height: 30))
label.text = "Hello, World!"
label.font = UIFont.systemFont(ofSize: 16)
label.textColor = UIColor.black
```
## 4 - button UI :
Créez un nouveau button

Définir le titre

Ajouter une cible et une action

```swift 
let button = UIButton(type: .system)
button.setTitle("Click Me", for: .normal)
button.addTarget(self, action: #selector(buttonTapped), for: .touchUpInside)

```
## 5 - UITextField :
Créez un nouveau champ de texte

Définir un espace réservé 

Définir le délégué 

```swift 
let textField = UITextField(frame: CGRect(x: 0, y: 0, width: 200, height: 30))
textField.placeholder = "Enter text"
textField.delegate = self
```
## 6 - UIImageView :
Créez une nouvelle vue d'image 

Définir l'image 

Définir le mode de contenu

```swift 
let imageView = UIImageView(frame: CGRect(x: 0, y: 0, width: 100, height: 100))
imageView.image = UIImage(named: "imageName")
imageView.contentMode = .scaleAspectFit
```
## 7 - UITableView :
Créez une nouvelle vue de tableau

Définir la source de données et déléguer 

Enregistrez une cellule 

```swift 
let tableView = UITableView(frame: CGRect(x: 0, y: 0, width: 200, height: 300), style: .plain)
tableView.dataSource = self
tableView.delegate = self
tableView.register(UITableViewCell.self, forCellReuseIdentifier: "CellIdentifier")
```
## 8 - UINavigationController :
Créez un contrôleur de navigation 

Poussez un nouveau contrôleur de vue 

Ouvrez le contrôleur de vue supérieur 

```swift 
let viewController = UIViewController() // Replace with your own view controller
let navigationController = UINavigationController(rootViewController: viewController)
navigationController.pushViewController(newViewController, animated: true)
navigationController.popViewController(animated: true)
```

## Exemple du code détaillé :

```swift 
import UIKit

// Créer une nouvelle UIWindow
let window = UIWindow(frame: UIScreen.main.bounds)

// Définir le contrôleur de vue principal (root view controller)
window.rootViewController = viewController

// Rendre la fenêtre visible
window.makeKeyAndVisible()

// Créer une nouvelle UIView
let view = UIView(frame: CGRect(x: 0, y: 0, width: 100, height: 100))

// Définir la couleur d'arrière-plan de la view
view.backgroundColor = UIColor.red

// Définir le rayon de coin de la view
view.layer.cornerRadius = 10

// Définir l'épaisseur et la couleur de la bordure de la view
view.layer.borderWidth = 1
view.layer.borderColor = UIColor.black.cgColor

// Ajouter une sous-view à la view
parentView.addSubview(sousview)

// Créer un nouveau UILabel
let label = UILabel(frame: CGRect(x: 0, y: 0, width: 200, height: 30))

// Définir le texte de l'étiquette
label.text = "Bonjour, monde !"

// Définir la police de l'étiquette
label.font = UIFont.systemFont(ofSize: 16)

// Définir la couleur du texte de l'étiquette
label.textColor = UIColor.black

// Créer un nouveau UIButton
let button = UIButton(type: .system)

// Définir le titre du button
button.setTitle("Cliquez-moi", for: .normal)

// Ajouter une cible (target) et une action au button
button.addTarget(self, action: #selector(buttonTapped), for: .touchUpInside)

// Créer un nouveau UITextField
let textField = UITextField(frame: CGRect(x: 0, y: 0, width: 200, height: 30))

// Définir le texte d'indication (placeholder) du champ texte
textField.placeholder = "Entrez du texte"

// Définir le délégué du champ texte
textField.delegate = self

// Créer une nouvelle UIImageView
let imageview = UIImageView(frame: CGRect(x: 0, y: 0, width: 100, height: 100))

// Définir l'image de la view image
imageview.image = UIImage(named: "nomDeLimage")

// Définir le mode de contenu de la view image
imageview.contentMode = .scaleAspectFit

// Créer une nouvelle UITableView
let tableview = UITableView(frame: CGRect(x: 0, y: 0, width: 200, height: 300), style: .plain)

// Définir la source de données et le délégué de la table view
tableview.dataSource = self
tableview.delegate = self

// Enregistrer une cellule pour la table view
tableview.register(UITableViewCell.self, forCellReuseIdentifier: "IdentifiantCellule")

// Créer un UINavigationController
let navigationControleur = UINavigationController(rootViewController: viewController)

// Empiler (push) un nouveau contrôleur de view sur la pile de navigation
navigationControleur.pushViewController(nouveauControleurDeview, animated: true)

// Retirer (pop) le contrôleur de view supérieur de la pile de navigation
navigationControleur.popViewController(animated: true)
```