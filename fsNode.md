# CREATION D'UNE STRUCTURE DE DOSSIER ET FICHIERS AVEC MODULE FS DE NODE 

## Detail du fichier .mjs sur préparation projet REACT du repo => [ICI](https://github.com/jimmyomont/initializeProjectReact)

```mjs
// Importation du module fs (système de fichiers) de Node.js
import fs from 'node:fs';

// Utilisation de la méthode forEach pour parcourir les arguments en ligne de commande à partir du troisième argument
process.argv.slice(2).forEach((projetName) => { 
// Définition du chemin racine
const root = "./";
// Définition du chemin du dossier src
const src = "./src"; 
// Création du dossier src s'il n'existe pas déjà
fs.mkdirSync(src); 
// Contenu du fichier HTML
const htmlContent = `
<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta http-equiv="X-UA-Compatible" content="IE=edge">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<script src="./index.js" defer type="module"></script>
    
<title>${projetName}</title>
</head>
<body>
    <div id="app"></div>
</body>
</html>`
// Écriture du contenu HTML dans le fichier index.html du dossier src
fs.writeFileSync(src + '/index.html', htmlContent); 

const jsContent = `
import { createRoot } from "react-dom/client";
import   App  from "./components/App";

const domElement = document.getElementById('app');
const root = createRoot(domElement);
root.render(<App />);`
// Écriture du contenu JavaScript dans le fichier index.js du dossier src
fs.writeFileSync(src + '/index.js', jsContent); 
// Contenu du fichier .gitignore
const gitignoreContent = ` 
node_modules
.parcel-cache
dist
`
// Écriture du contenu dans le fichier .gitignore à la racine du projet
fs.writeFileSync(root + '/.gitignore', gitignoreContent ); 
// Définition du chemin du dossier components
const component = "./src/components" 
// Création du dossier components
fs.mkdirSync(component); 
// Définition du chemin du dossier App dans components
const app = "./src/components/App" 
// Création du dossier App dans components
fs.mkdirSync(app); 
// Contenu du fichier index.js de App
const appContent = ` 
import Header from "../Header";
import Main from "../Main";
import Footer from "../Footer";
import './style.scss'
            
function App(){
    return(
        <>
        <Header />
        <Main />
        <Footer />
        </>
        );
    }
export default App;`
// Écriture du contenu JavaScript dans le fichier index.js du dossier App
fs.writeFileSync(app + '/index.js', appContent); 

const scssContent = `body{
    margin: 0;
    padding: 0;
    border: 0;
}`
// Écriture du contenu SCSS dans le fichier style.scss du dossier App
fs.writeFileSync(app + '/style.scss', scssContent); 
// Définition du chemin du dossier Header dans components
const header = "./src/components/Header" 
// Création du dossier Header dans components
fs.mkdirSync(header); 
// Contenu du fichier index.js de Header
const headerContent = ` 
import './style.scss';

function Header() {
    return (
    <div className="header">
    <h1>Ceci est le Header de ton projet : ${projetName}🥳</h1>
    </div>
    );
}

export default Header;
`;
// Écriture du contenu JavaScript dans le fichier index.js du dossier Header
fs.writeFileSync(header + '/index.js', headerContent); 
const headerScss = `.header{
}`
// Écriture du contenu SCSS dans le fichier style.scss du dossier Header
fs.writeFileSync(header + '/style.scss', headerScss); 
// Définition du chemin du dossier Main dans components
const main = "./src/components/Main" 
// Création du dossier Main dans components
fs.mkdirSync(main); 
// Contenu du fichier index.js de Main
const mainContent = ` 
import './style.scss';

function Main() {
    return (
        <div className="main">
        <h2>Le main du projet 💪</h2>
        </div>
        );
    }
    
    export default Main;
    `;
// Écriture du contenu JavaScript dans le fichier index.js du dossier Main
fs.writeFileSync(main + '/index.js', mainContent); 
const mainScss = `.main{
}`
// Écriture du contenu SCSS dans le fichier style.scss du dossier Main
fs.writeFileSync(main + '/style.scss', mainScss); 
// Définition du chemin du dossier Footer dans components
const footer = "./src/components/Footer" 
// Création du dossier Footer dans components
fs.mkdirSync(footer); 
// Contenu du fichier index.js de Footer
const footerContent = ` 
import './style.scss';

function Footer() {
    return (
    <div className="footer">
        <h3>et le footer ✌️.. maintenant tu peux supprimer ce contenu et travailler dur en t'amusant 😇!!!</h3>
    </div>
    );
}

export default Footer;
`;
// Écriture du contenu JavaScript dans le fichier index.js du dossier Footer
fs.writeFileSync(footer + '/index.js', footerContent); 
const footerScss = `.footer{
}`
// Écriture du contenu SCSS dans le fichier style.scss du dossier Footer
fs.writeFileSync(footer + '/style.scss', footerScss); 
});
```