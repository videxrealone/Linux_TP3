# Cours Linux 
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------
# Linux - TP 3 :

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------

## Exercice 1 : Les Liens
* **Question 1:** Créez l’arborescence de la figure ?? dans votre répertoire personnel.

![image](https://user-images.githubusercontent.com/91763346/201353239-f6e04d71-0518-4012-92e0-429f7fd0e62a.png)

* **Question 2:** À l’aide de la commande echo, écrivez « Il fait beau aujourd’hui. » dans le fichier fic6.

![image](https://user-images.githubusercontent.com/91763346/201353634-dea369ab-2bf3-4892-b3e5-a95ecebd5e19.png)

* **Question 3:** À l’aide de la commande cat, affichez le contenu du fichier fic6 depuis le répertoire rep2.

![image](https://user-images.githubusercontent.com/91763346/201353860-62d59270-3fc8-4f08-8d99-920035995fca.png)


* **Question 4:** L’option -l de la commande ls permet entre autre d’observer les droits d’un fichier et/ou répertoire. À quoi correspondent les autres informations que l’on obtient grâce à cette commande ?

![image](https://user-images.githubusercontent.com/91763346/201354867-d53cd8a6-a712-4d18-ab24-647260ab3715.png)
la commande ls -l affiche en format **LONG** les informations des fichiers du répertoire actuel

* **Question 5:** À l’aide de la commande ln, créez un lien physique sur le fichier fic6 dans test sous le nom lpfic6. 

![image](https://user-images.githubusercontent.com/91763346/201355962-eaf3426d-0e68-4867-9ead-d44ece00eb12.png)

* **Question 6:** Modifiez le fichier lpfic6 à l’aide de la commande echo. Que constatez-vous dans le fichier fic6 ? Réciproquement, modifiez fic6 et lisez lpfic6. Que concluez-vous ?

![image](https://user-images.githubusercontent.com/91763346/201356176-d5249e3c-b779-4a2f-9d64-c6426e21dd23.png)
![image](https://user-images.githubusercontent.com/91763346/201356603-e5372250-e6df-4bc3-9c1c-0aab169847f8.png)

* **Question 7:** Modifiez les droits au fichier fic6 pour les membres du groupe. Que constatez-vous pour
lpfic6 ? Donnez une explication.

![image](https://user-images.githubusercontent.com/91763346/201356841-70ceaaa2-9eeb-402b-b206-c6561cbfd9bc.png)


* **Question 8:** La commande ln peut aussi créer des liens symboliques avec l’option -s. Créez un lien symbolique sur le fichier fic6 dans test que vous appellerez lsfic6.

![image](https://user-images.githubusercontent.com/91763346/201356997-da22b551-8bb9-4533-8ac7-6c72d6e2a4ea.png)

* **Question 9:** Regardez toutes les informations concernant les fichiers lpfic6 et lsfic6. Quelles diffé-
rences notez-vous ?

![image](https://user-images.githubusercontent.com/91763346/201357255-c3b4bf5e-d430-4451-8295-f4cfb2383c3f.png)

le fichier **lsfic6** est un fichier **LIEN** qui pointe sur -> **fic6** et qui admet tous les permissions.

* **Question 10:** Essayez de modifier les droits d’accès au fichier lsfic6. Que constatez- vous ?

![image](https://user-images.githubusercontent.com/91763346/201357806-2e742c19-0a87-4429-ab50-b1e4a757986c.png)
On ne peut pas changer les permissions d'un fichier symbolique.

* **Question 11:** Modifiez les droits d’accès au répertoire rep1 pour ne plus y avoir accès. Essayez d’afficher le contenu de lpfic6 et lsfic6. Que constatez-vous ? Donnez une explication.

![image](https://user-images.githubusercontent.com/91763346/201358468-837afeef-454e-4cf0-927f-cc9a456efbfd.png)
On ne peut pas accèder au **rep1** et donc le lien **lspic6** n'est plus accessible car il ne peut plus pointer sur un fichier qu'ill ne peut pas l'acceder.

* **Question 12:** Modifiez de nouveau les droits d’accès au répertoire rep1 pour y avoir de nouveau accès. Déplacez le fichier fic6 dans le répertoire rep1. Essayez d’afficher le contenu de lpfic6 et lsfic6. Que constatez-vous ?

![image](https://user-images.githubusercontent.com/91763346/201359435-df14397b-263b-41de-b5f9-cb957ef234dd.png)

* Le fichier **lsfic6** n'est plus lisible car on a déplacé le fichier qu'il pointe dessus **fic6**.
* Le fichier **lpfic6** est encore lisible car il fonctionne comme un fichier copie sur **fic6** donc il conserver son contenu.

* **Question 13:** Redéplacez le fichier fic6 dans le répertoire rep4. Essayez à nouveau d’afficher le contenu de lpfic6 et lsfic6. Supprimez le fichier fic6 puis recommencez. Que constatez-vous ?
![image](https://user-images.githubusercontent.com/91763346/201360223-e04c8d7f-fc3a-4155-9ce0-053843ed8fc8.png)
![image](https://user-images.githubusercontent.com/91763346/201360419-394311b1-3be1-4249-ab65-787d47a5cddf.png)
Comme **lpfic6** est une copie physique (lien physique), le fichier **lfpic6** conserve le contenu du **fic6**
Comme **lsfic6** est une copie symbolique donc il doit toujours avoir access au fichier **fic6** donc si **fic6** est introuvable, le fichier **lsfic6** ne fonctionne plus.

* **Question 14:** Recréez le fichier fic6 dans le répertoire rep4, de manière à ce que **test/lpfic6** et **test/rep1/rep4/fic6** désignent de nouveau le même fichier.
![image](https://user-images.githubusercontent.com/91763346/201361455-92c68d45-217a-4c02-89f8-8cb4592bad39.png)
![image](https://user-images.githubusercontent.com/91763346/201363620-bf620095-7878-446a-ad40-32a00d822b9c.png)

## Exercice 2 : Les i-nodes

* **Question 1:** À l’aide de la commande ls munie de l’option appropriée (ouvrir man ls et chercher inode), observez le numéro d’i-nœud du fichier fic2. Copiez le fichier fic2 dans le répertoire rep2. Quel est son numéro d’i-nœud ?

![image](https://user-images.githubusercontent.com/91763346/201362095-e1c33238-b5c1-4589-96a1-8640d1cc7c2e.png)

![image](https://user-images.githubusercontent.com/91763346/201362387-574a67c5-02b5-41fe-9d15-8371b4bcb6df.png)

Les **inodes** des deux copies sont différents.

* **Question 2:** Changez le nom de ce dernier fichier, pour l’appeler fic7. Le numéro d’i-nœud change-t-il ?
![image](https://user-images.githubusercontent.com/91763346/201362818-1b1561f3-0b8f-4f20-901c-2bc7b84e3b5a.png)
Non le **inode** ne change pas.

* **Question 3:** Comparez les numéros d’i-nœud entre le fichier fic6 du répertoire rep4, lpfic6 et lsfic6.
Que remarquez-vous ?
![image](https://user-images.githubusercontent.com/91763346/201363864-22c3f9ae-78ae-4dca-9ec3-4dc242168d75.png)
Les fichiers **lsfic6** et **fic6** ont le meme **inode** mais le **lpfic6** et **fic6** ont des differents **inodes**.

