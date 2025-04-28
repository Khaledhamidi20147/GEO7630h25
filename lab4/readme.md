# 🌍 Traitement et Diffusion de Rasters avec PostgreSQL/PostGIS

## 🎯 Objectif
Développer des compétences pratiques sur :
- 📥 Lecture et traitement de rasters (TIF, GeoTIFF, PNG)
- 🛠️ Extraction de valeurs raster en données vectorielles
- 🗄️ Stockage de rasters dans PostgreSQL/PostGIS
- 🧩 Génération de tuiles raster et pyramides d'affichage
- 🔗 Association de valeurs Z aux objets vectoriels

---

## 📂 Données utilisées
➡️ [Accéder aux données du laboratoire](https://drive.google.com/drive/folders/1iRcyRWS_JiTciNdonm8leC7Nq03hRY5_?usp=sharing)

---

## 🛠️ 1. Intégration d'images aériennes

### 🔄 Reprojection
- Projection vers **EPSG:32188** avec **Reprojector**.

![alt text](image.png)

### 🧩 Extraction de métadonnées
- Utilisation de **RasterPropertyExtractor** pour récupérer dimensions, bandes et types de données.

![alt text](image-1.png)

### 🌀 Rééchantillonnage
- **RasterResampler** pour diviser colonnes/rangées par 10 et réduire la résolution.

![alt text](image-2.png)

### 🧱 Création de pyramides
- **RasterPyramider** pour optimiser l'affichage rapide à différents niveaux de zoom.

![alt text](image-3.png)

### 🖋️ FeatureWriter & Visualisation SQL
- Utilisation de **FeatureWriter** pour chaîner traitements + **SQLExecutor** pour inspection finale en base.

![alt text](image-4.png)  ![alt text](image-5.png)
---

## 🛠️ 2. Traitement d'îlots de chaleur

### 🔄 Reprojection
- Projection vers **EPSG:32188**.

![alt text](image-6.png)

### 📐 Conversion en vecteurs
- **RasterToPolygonCoercer** pour convertir rasters en polygones (classification).

![alt text](image-7.png) ![alt text](image-8.png)

### 🖥️ Stockage PostGIS
- Export des polygones vers une base PostGIS et visualisation dans QGIS.

![alt text](image-9.png)

### 🎨 Amélioration visuelle
- **RasterDiffuser** (lissage) et **RasterCellValueRounder** (arrondi à 1 décimale).
- Nouvelle conversion en polygones pour une meilleure lisibilité.

![alt text](image-10.png)

### 🔄 Conversion avancée
- **RasterCellCoercer** pour transformer en points, lignes, polygones pour analyses plus riches.

![alt text](image-11.png)
---

## 🛠️ 3. Génération de courbes de niveau depuis un MNS

### 📈 Création des courbes de niveau
- **ContourGenerator** pour générer les courbes à partir du MNS.

### ✨ Simplification
- **Generalizer** pour réduire le nombre de sommets et alléger les données.

### 🧩 Construction de surfaces
- **AreaBuilder** pour transformer les lignes de contour en polygones.

![alt text](image-12.png)

### 🖥️ Visualisation finale
- Chargement des surfaces générées dans PostGIS et visualisation dans QGIS.

![alt text](image-13.png)

![alt text](image-14.png)

![alt text](image-15.png)

---
