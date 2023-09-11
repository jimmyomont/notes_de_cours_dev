# PHPMAILER

### Étape 1 : Installation de PHPMailer

1. **Téléchargez PHPMailer** :
   Rendez-vous sur le site officiel de PHPMailer à l'adresse https://github.com/PHPMailer/PHPMailer et téléchargez la dernière version de la bibliothèque.

2. **Extraction des fichiers** :
   Extrayez le contenu de l'archive ZIP téléchargée dans le répertoire de votre projet.

3. **Structure du projet** :
   Assurez-vous que votre structure de projet ressemble à ceci :
   ```
   /votre_projet/
   ├── PHPMailer/
   │   ├── src/
   │   ├── ...
   ├── votre_script.php
   ```

### Étape 2 : Configuration de PHPMailer

1. **Incluez la bibliothèque** :
   Dans votre script PHP où vous souhaitez utiliser PHPMailer, incluez la bibliothèque en utilisant la ligne suivante en haut de votre fichier :
   ```php
   use PHPMailer\PHPMailer\PHPMailer;
   use PHPMailer\PHPMailer\SMTP;
   use PHPMailer\PHPMailer\Exception;
   require 'PHPMailer/src/PHPMailer.php';
   require 'PHPMailer/src/SMTP.php';
   require 'PHPMailer/src/Exception.php';
   ```

2. **Créez une instance de PHPMailer** :
   Vous pouvez maintenant créer une instance de PHPMailer dans votre script :
   ```php
   $mail = new PHPMailer(true); // Le paramètre true active les exceptions pour la gestion des erreurs.
   ```

3. **Configurer les paramètres SMTP** :
   Vous devez configurer les paramètres SMTP pour envoyer des e-mails. Voici un exemple pour Gmail :
   ```php
   $mail->isSMTP();
   $mail->Host       = 'smtp.gmail.com';
   $mail->SMTPAuth   = true;
   $mail->Username   = 'votre_adresse_email@gmail.com';
   $mail->Password   = 'votre_mot_de_passe';
   $mail->SMTPSecure = PHPMailer::ENCRYPTION_STARTTLS;
   $mail->Port       = 587;
   ```

### Étape 3 : Envoi d'un e-mail

1. **Paramètres de l'e-mail** :
   Configurez les détails de l'e-mail, y compris le destinataire, l'expéditeur, le sujet et le contenu :
   ```php
   $mail->setFrom('votre_adresse_email@gmail.com', 'Votre Nom');
   $mail->addAddress('adresse_destinataire@example.com', 'Nom du destinataire');
   $mail->Subject = 'Sujet de l\'e-mail';
   $mail->Body    = 'Contenu de l\'e-mail en HTML ou texte brut';
   ```

2. **Pièces jointes (optionnel)** :
   Vous pouvez ajouter des pièces jointes à l'e-mail si nécessaire :
   ```php
   $mail->addAttachment('chemin_vers_la_piece_jointe.pdf');
   ```

3. **Envoi de l'e-mail** :
   Envoyez l'e-mail en utilisant la méthode `send` :
   ```php
   $mail->send();
   echo 'E-mail envoyé avec succès !';
   ```

4. **Gestion des exceptions** :
   Assurez-vous de gérer les exceptions pour capturer d'éventuelles erreurs lors de l'envoi de l'e-mail :
   ```php
   } catch (Exception $e) {
       echo "Erreur lors de l'envoi de l'e-mail : {$mail->ErrorInfo}";
   }
   ```
