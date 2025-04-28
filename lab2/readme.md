# 📚 Compte Rendu — Laboratoire 2

## 🚀 Introduction
Description des étapes suivies pour assurer le bon déroulement du **laboratoire 2**, en utilisant **FME Workbench** et **QGIS** pour un traitement spatial avancé.

---

## 🛠️ Matériel et Méthodes

### ⚙️ Matériel utilisé
- **FME Workbench**
- **QGIS**

---

### 📅 Méthodologie

#### 📝 Étapes principales

### 1. Création d'un projet FME 📂
- Ouvrir **FME Workbench**.
- Créer un **nouveau projet**.

---

### 2. Lecture des fichiers CSV et GeoJSON 📖
- **Sources** : Arbres de Montréal et Quartiers.
- Connexion via **Reader** avec liens directs (pas besoin de téléchargement manuel).

![image](https://github.com/user-attachments/assets/4c6546f1-fd1d-4e8d-b613-fe71e1f2f097)
![image](https://github.com/user-attachments/assets/b01db50b-fd02-4573-9c3c-4c931bb3b1d8)
![image](https://github.com/user-attachments/assets/3b1b22db-8371-4911-a459-b0dda066ba30)

✅ Connexion réussie sans erreurs !

⚠️ **Correction d'encodage** :

![image](https://github.com/user-attachments/assets/85198a41-f22a-4aca-a6bd-e8486d352796)

✔️ Problèmes d'écriture corrigés :

![image](https://github.com/user-attachments/assets/d42d0a9e-8fe7-4398-9c7d-1217306bd762)

---

### 3. Reprojection en MTM8 (EPSG:32188) 🗺️
- Alignement précis des couches.
- Réduction des distorsions locales.

![image](https://github.com/user-attachments/assets/ce14da8c-8bf4-4fd1-8fbc-fcbd792f44eb)

---

### 4. Jointure spatiale (Points dans Polygones) 📌
- Utilisation de **PointOnAreaOverlayer** pour compter les arbres par quartier.

![image](https://github.com/user-attachments/assets/e4dd89b1-7697-428f-9e5f-3b62a1ceca46)
![image](https://github.com/user-attachments/assets/bc9aacb5-11a3-4fdb-87c8-761c75d1be77)

---

### 5. Nettoyage et modification des attributs 🧹
- Utilisation de **AttributeManager** pour :
  - Supprimer les attributs inutiles.
  - Renommer proprement.

![image](https://github.com/user-attachments/assets/1ac34dea-91d3-4e95-adea-2bf50558ad8e)

---

### 6. Calcul de statistiques 📈
- Application d'une formule personnalisée :

![image](https://github.com/user-attachments/assets/0caf301d-d385-4443-bf45-9a96043243ac)
![image](https://github.com/user-attachments/assets/26829d06-0540-456f-b947-b8c4c9d85a1c)
![image](https://github.com/user-attachments/assets/018a2c40-cbe2-4cd5-bcd5-01e5f99c53ee)

✅ Résultat obtenu :

![image](https://github.com/user-attachments/assets/6b5de571-01ef-4ca0-81a1-72f5356a930b)

---

### 7. Exportation vers QGIS 🌐
- Export des résultats via **Writer PostGIS**.



---

### 8. Visualisation sous QGIS 🎨
- Chargement de la couche dans QGIS.

![alt text](image-1.png)

---

### 9. Symbologie avancée 🖌️
- Application d'un style basé sur la **quantité d'arbres** par quartier.
- Ajout d'un fond de carte **ESRI** :

![alt text](image-2.png)


---

### 10. Résultat final 🎯
- Aperçu dans FME :

![alt text](image.png)

---


---

