# Compte Rendu du laboratoire 3 :



### Matériel
- FME Workbench 
- QGIS

### Étapes
1. Étape 1 :Ouvrir FME et Création d'un nouveau projet :
2. Étape 2 :Lecture du CSV 

   1- Input : Arbres et Parcs de la ville de montréal 
Avec les données d'adresse,Longitude et Latitude

Ces données sont extraites du site des données ouvertes de la ville de Montréal

   Arbres en CSV ;
   
![image](https://github.com/user-attachments/assets/13d2cf26-b5ce-4d44-8eb4-a3324ff92787)

 Parcs en GeoJson ;

 ![image](https://github.com/user-attachments/assets/d5eca360-0d62-42ea-b4f6-698dfe764bd5)
 

![image](https://github.com/user-attachments/assets/324d9994-5fa7-4186-982a-3946f27c28d5)


3. 🌍 Étape 3 : Reprojection des données

Reprojeter les couches de données (arbres et parcs) en EPSG:32188.
Utiliser le transformer Reprojector dans FME.

![image](https://github.com/user-attachments/assets/352ca51f-caba-4962-adc6-285d28d0ffb5)




4. Étape 4 : Jointure spatiale
   
Pour cette étape de jointure on faire joindre chaque arbres a chaque parcs  qui le contient :

![image](https://github.com/user-attachments/assets/a6d0f559-aaef-4766-9eee-1f151971caf9)



![image](https://github.com/user-attachments/assets/28be6df4-758e-4065-ad82-36a2a5b8dd67)

5. Étape 5 : Nettoyage :

Pour cette étape L'attribute keeper fera notre affaire

   ![image](https://github.com/user-attachments/assets/142ab431-9eb1-4ff4-be7d-f62e13f525bb)

 
6. Étape 6 : Calcul :

l'attribute creator pour ajouter une case de calcul de densité d'arbres pour chaque parc :

![image](https://github.com/user-attachments/assets/0fdfdad7-66dc-4f7a-8d6a-542906cd2379)

![image](https://github.com/user-attachments/assets/27143600-4a67-490a-82cb-b45e84222914)

![image](https://github.com/user-attachments/assets/c79bfaef-8d24-4fcc-b3bf-119e199a993d)

Puis on calculera la mediane en utilisant le statistic calculator :

![image](https://github.com/user-attachments/assets/7c039578-32be-4ae5-8e8e-e763398a3ee0)

l'index de densité comme suit avec l'attribute manager :

![image](https://github.com/user-attachments/assets/746b4828-c598-4d5c-a295-19eaeba8a6ce)


![image](https://github.com/user-attachments/assets/41c41f8a-95a3-4185-8c6f-28427281f291)




7. Étape 7 : dernier nettoyage :
   
   Un nettoyage rigoureux garantit une base de données uniforme et fiable, en remplaçant les valeurs vides ou incorrectes par des valeurs nulles pour éviter les incohérences.
   
pour cela on va utiliser un null attribute manager

![image](https://github.com/user-attachments/assets/ca668ab5-78ff-40ab-aa9e-f6f67b6d20a5) 


8. Étape 8 : Exportation vers QGIS

On exporte nos données avec le writer pour une visualisation sur QGIS 

![alt text](image-1.png)

   
9. Étape 9 : Visualisation sur QGIS

![alt text](image.png)


   PARTIE 2 DU LABO

   
   
10. Étape 10 : Création d’une grille hexagonale :

   on commence par connecter les données des parcs à un H3HexagonalIndexer et le configurer: 

   ![image](https://github.com/user-attachments/assets/f51df78a-2fbd-4c48-83ab-d4989128e5a5)

11. Étape 11 : Jointure spatiale avec les arbres :

    Pour la jointure on utilisera le pointonAreaOverLayer :

    ![image](https://github.com/user-attachments/assets/89d11642-420f-4602-8578-822a673ec2e6)

12. Étape 12 : Selection des attributs :

    On selectionne les attributs a garder avec l'attribute Keeper

![image](https://github.com/user-attachments/assets/f84eac56-7e6f-46bf-886e-b714314b652e)


Puis on renomme un attribut :

![image](https://github.com/user-attachments/assets/0396d7b0-4404-495f-8a49-f99ff463643a)


    
13. Étape 13 : Exportation vers QGIS :

    Cela se fait avec un writer postgis
    
    ![alt text](image-2.png)

14. Étape 14 : Visualisaton QGIS :

    Aprés l'exportation on travaille sur une palette de couleur et un joli classement pour avoir le résultat suivant

    ![alt text](image-3.png)





