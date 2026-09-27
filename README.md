# 👁️ Vision Artificielle : De la Traitement d'Image Classique (OpenCV) à YOLOv8

> **"Arrêtons le hype LinkedIn."**  
> Beaucoup de démos dites « IA révolutionnaires » qu'on voit passer sur les réseaux sociaux reposent sur des algorithmes de vision par ordinateur extrêmement matures qui existent depuis plus de 30 ans. Ce dépôt démontre comment combiner la **vision algorithmique classique (OpenCV)** et les **réseaux de neurones profonds (YOLOv8)** pour obtenir des résultats performants, temps réel et frugaux sans sur-ingénierie.

🎥 **Tutoriel vidéo associé :** [Vision artificielle et YOLO v8 — Le Lab IA](https://www.youtube.com/watch?v=YSF4Hh4YxKY)

---

## 📌 Philosophie du projet

1. **Démystifier la vision artificielle** : Pas besoin de GPU de compétition ni de modèles de plusieurs milliards de paramètres pour calculer un centre de gravité, suivre un mouvement ou binariser un document.
2. **Hybridation des approches** : La vraie vision industrielle associe le filtrage pré-IA (égalisation d'histogrammes, seuillage, détection de contours) et les modèles CNN/YOLO pour la classification complexe.
3. **Approche pragmatique & Open Source** : Du code Python léger, lisible, commenté et prêt à exécuter en local.

---

## 🗂️ Structure des dépôts

Le projet se découpe en deux piliers complémentaires :

| Dépôt / Module | Techno | Description |
| :--- | :--- | :--- |
| **`Tutorial.Vision.01.OpenCV`** | Python 3, OpenCV | Traitement d'image classique, histogrammes, détection de mouvements, extraction de primitives, calcul du centre de gravité sans IA. |
| **`Tutorial.Vision.02.Yolo`** | Python 3, YOLOv8, OpenCV | Détection d'objets/personnes temps réel, détection de collisions/overlap, export structuré (JSON & ElasticSearch). |

---

## ⚙️ Fonctions & Démonstrations

### 1. Vision Classique (OpenCV)
* **Analyse d'histogrammes** : Manipulation de la luminosité/exposition/contraste pour détacher les objets du fond (principe tiré des fondamentaux de la vision industrielle comme *The Pocket Handbook of Image Processing Algorithms in C*, 1993).
* **Détection de mouvement & Centroiding** : Extraction des zones actives par différenciation d'images et calcul du centre de gravité (croix cible) sans surcoût matériel.

### 2. Détection & Analyse d'Objets (YOLOv8)
* **`01_gravity_center.py`** : Détection de personnes/objets avec calcul dynamique de la Bounding Box et extraction de ses coordonnées centrales ($X, Y$).
* **`02_collision_overlap.py`** : Calcul d'overlap (chevauchement) entre deux patatoïdes / Bounding Boxes pour déclencher des alertes de proximité / collision.
* **Intégration & Export Data** :
  * Génération de logs d'événements au format **JSON**.
  * Indexation et envoi des métadonnées de détection temps réel vers un cluster **ElasticSearch**.

---

## 🚀 Prise en main rapide

### Prérequis

* **Python 3.10+**
* Une webcam fonctionnelle (device `0` ou ajuster l'index dans le script).

### Installation

```bash
# 1. Cloner le dépôt
git clone [https://github.com/jeromefortias/Tutorial.Vision.02.Yolo.git](https://github.com/jeromefortias/Tutorial.Vision.02.Yolo.git)
cd Tutorial.Vision.02.Yolo

# 2. Créer et activer un environnement virtuel
python -m venv venv
source venv/bin/activate  # Sur Linux/macOS
# venv\Scripts\activate   # Sur Windows

# 3. Installer les dépendances
pip install -r requirements.txt
