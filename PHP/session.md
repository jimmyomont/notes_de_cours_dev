# SESSION PHP

## Liste des sessions_ :

- **session_name()**: 

Cette fonction permet de définir ou d'obtenir le nom de la session. Par défaut, le nom de session est généralement "PHPSESSID". Vous pouvez utiliser cette fonction pour personnaliser le nom de la session, ce qui peut être utile pour éviter les conflits de cookies avec d'autres applications ou scripts sur le même domaine.

- **session_destroy()**: 

Cette fonction est utilisée pour détruire complètement la session courante. Elle supprime toutes les données de session associées à l'utilisateur et détruit l'identifiant de session. Cela permet de forcer la déconnexion de l'utilisateur ou de terminer une session lorsque cela est nécessaire.

- **session_start()**: 

Cette fonction est essentielle pour démarrer une session PHP ou reprendre une session existante. Elle initialise la gestion des sessions, crée un nouvel identifiant de session si nécessaire et permet d'accéder aux données de session stockées dans $_SESSION.

- **session_status()** :

    Est utilisée pour obtenir l'état courant de la session PHP en cours d'exécution. Elle retourne l'une des trois constantes possibles :

    - **PHP_SESSION_DISABLED** : Cette constante indique que les sessions sont désactivées sur le serveur PHP. En d'autres termes, PHP ne prend pas en charge la gestion des sessions. Si vous obtenez cette valeur, cela signifie que vous ne pouvez pas utiliser de sessions dans votre application.

    - **PHP_SESSION_NONE** : Cette constante indique que les sessions sont activées sur le serveur PHP, mais aucune session n'a été démarrée dans le script en cours. Cela signifie qu'aucune donnée de session n'est actuellement disponible. Vous pouvez utiliser cette valeur pour déterminer si une session a déjà été démarrée avant d'en commencer une nouvelle.

    - **PHP_SESSION_ACTIVE** : Cette constante indique qu'une session est déjà active dans le script en cours. Cela signifie que les données de session sont disponibles pour être lues et modifiées à partir de la variable superglobale $_SESSION. Si cette valeur est renvoyée, vous pouvez interagir avec la session.

- **session_id()**: 

Cette fonction permet d'obtenir ou de définir l'identifiant de la session courante. Vous pouvez l'utiliser pour récupérer l'identifiant de session actuel ou pour définir un nouvel identifiant de session.

- **session_regenerate_id()**: 

Cette fonction génère un nouvel identifiant de session et le remplace par l'identifiant actuel. Cela est utile pour renouveler l'identifiant de session lorsqu'un utilisateur se connecte ou effectue une action importante, ce qui renforce la sécurité.

- **session_unset()**: 

Cette fonction supprime toutes les variables de session. Cependant, elle ne détruit pas la session elle-même, donc l'identifiant de session reste le même.

- **session_write_close()**: 

Cette fonction permet de fermer la session courante tout en laissant les données de session accessibles. Cela peut être utile lorsque vous souhaitez libérer la session pour permettre à d'autres scripts de l'utiliser tout en évitant des problèmes de verrouillage.

- **session_cache_expire()**: 

Vous pouvez utiliser cette fonction pour définir la durée d'expiration de la session en minutes. Elle détermine combien de temps une session reste active après la dernière activité de l'utilisateur. Par défaut, c'est généralement de 24 minutes.

- **$_SESSION**: 

Cette superglobale est utilisée pour stocker des données de session. Vous pouvez y accéder pour lire ou écrire des variables de session. Par exemple, $_SESSION['nom_variable'] permet de stocker et d'accéder à une variable de session.

- **$_COOKIE[session_name()]**: 

Cette superglobale vous permet d'accéder à l'identifiant de session stocké dans un cookie. Vous pouvez l'utiliser pour obtenir l'identifiant de session actuel, mais généralement, cela est géré automatiquement par PHP.

- **session_set_save_handler()**: 

Cette fonction avancée vous permet de définir des gestionnaires personnalisés pour les sessions. Vous pouvez créer votre propre logique de stockage de session en utilisant cette fonction.

- **session_module_name()**: 

Vous pouvez l'utiliser pour obtenir ou définir le nom du module de gestion de session utilisé par PHP. Par défaut, PHP utilise le module "files" pour stocker les données de session sur le serveur, mais vous pouvez le personnaliser en utilisant cette fonction.

- **session_gc()**: 

Cette fonction permet de nettoyer les sessions obsolètes en supprimant les données de session expirées. Vous pouvez l'utiliser pour maintenir propre le stockage des sessions sur le serveur.

- **session_set_cookie_params()**: 

Vous pouvez utiliser cette fonction pour définir les paramètres du cookie de session, tels que le chemin, le domaine, la durée de validité, et d'autres attributs. Elle vous permet de personnaliser la manière dont les cookies de session sont gérés par PHP.

- **session_cache_limiter()**: 

Cette fonction permet de définir le comportement de mise en cache des pages contenant des données de session. Vous pouvez contrôler les en-têtes de mise en cache pour garantir que les données de session sont gérées correctement par le navigateur.

- **session_save_path()**: 

Cette fonction vous permet de définir le chemin où les données de session sont stockées sur le serveur. Vous pouvez spécifier un répertoire personnalisé pour stocker les fichiers de session.

- **session_get_cookie_params()**: 

Vous pouvez utiliser cette fonction pour obtenir les paramètres actuels du cookie de session, tels que le chemin, le domaine, la durée de validité, etc. Elle est utile si vous souhaitez connaître les valeurs actuelles des paramètres du cookie de session.

- **session_abort()**: 

Cette fonction permet d'abandonner la session en cours sans la détruire. Cela signifie que les données de session restent inchangées, mais la session est marquée comme abandonnée. Vous pouvez ensuite reprendre la session avec session_start().

- **session_reset()**: 

Cette fonction réinitialise la session courante à ses valeurs initiales. Toutes les modifications apportées aux variables de session depuis le début de la session seront annulées.






