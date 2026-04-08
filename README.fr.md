> 🇬🇧 [Read in English](README.md)

# HeatMyFloor - Application de conception de plancher chauffant

Application desktop Java pour modéliser et concevoir des systèmes de plancher chauffant avec génération automatique des chemins de câbles.

**Projet universitaire d'équipe** - Développé collaborativement dans le cadre des cours IFT-2007/GLO-2004 à l'Université Laval (Automne 2025).
> Le dépôt original du cours est privé. Ce miroir contient uniquement ce README.

## 📹 Démo

![Demo](Demo%20Heatmyfloor.gif)

*Vidéo complète : [https://1drv.ms/v/c/8c0ddc1208bfc810/IQA16OWgem3LRYmcMS83wAz0ASPZcuLVOPl9OH0SHJgrNiQ]*

## 📸 Captures d'écran

*Conception d'une pièce avec placement des meubles*
<img width="1920" height="1032" alt="image" src="https://github.com/user-attachments/assets/202b4cbb-64d4-49f9-83a5-9a6be08e023b" />

*Génération automatique du chemin de câbles chauffants*
<img width="1920" height="1032" alt="image" src="https://github.com/user-attachments/assets/f8293d21-de96-48f9-9280-5b008f259b9f" />

*Pièces de forme irrégulière avec contraintes*
<img width="1920" height="1032" alt="image" src="https://github.com/user-attachments/assets/1a12c3b3-b4e1-4370-970d-65808914da99" />

## ✨ Fonctionnalités

### Conception de la pièce
- **Pièces rectangulaires** avec dimensions personnalisables
- **Pièces polygonales irrégulières** avec placement interactif des points
- **Rendu visuel en temps réel** du plan de la pièce
- **Support multi-projets** via interface à onglets

### Meubles et objets
- **Placement par glisser-déposer** (avec ou sans drain)
- **Objets muraux**
- **Configuration de zones restreintes**
- **Détection de collision** et validation des limites
- **Repositionnement automatique** lors du redimensionnement

### Système de chauffage
- **Génération automatique du chemin de câbles** par algorithmes à contraintes
- **Contournement des obstacles** (meubles, murs, zones restreintes)
- **Génération de membrane chauffante**
- **Placement du thermostat**
- **Espacement et motifs de câbles** personnalisables

### Fonctionnalités avancées
- **Annuler/Rétablir** (patron de conception Mémento)
- **Sauvegarde/Chargement de projets** (persistance fichier)
- **Gestion des erreurs** avec retour visuel
- **Panneau de configuration** pour mesures précises
- **Export des plans**

## 🛠️ Technologies

- **Java** (application desktop)
- **Swing** (interface graphique)
- **Algorithmes de graphe personnalisés** pour la génération de chemins
- **Architecture hexagonale** (conception orientée domaine)

## 📁 Structure du projet
```
src/main/java/com/heatmyfloor/
├── domain/                    # Logique métier
│   ├── graphe/               # Algorithmes de graphe et génération de chemins
│   ├── items/                # Meubles, drains, zones
│   ├── piece/                # Modèles et contrôleurs de pièces
│   ├── ports/                # Interfaces (architecture hexagonale)
│   └── utilities/            # Point, Rect2D, mappeurs
├── gui/                      # Interface utilisateur
│   ├── MainWindow.java
│   ├── Canvas.java
│   ├── BarreOutils.java
│   ├── Proprietes.java
│   ├── PositionPanel.java
│   ├── drawer/               # Logique de rendu
│   └── FormeIrregulierPanel.java
├── infrastructure/           # Entrées/Sorties fichier
└── HeatMyFloor.java          # Point d'entrée
```

## 🚀 Installation et utilisation

### Prérequis
- Java JDK 11 ou supérieur
- Maven (optionnel, pour compiler depuis les sources)

### Téléchargement et exécution

Télécharger la dernière version : [📦 heatmyfloor.jar](./heatmyfloor.jar)
```bash
java -jar heatmyfloor.jar
```

## 📖 Guide d'utilisation

### Créer une pièce

1. **Pièce rectangulaire** : Cliquer sur "Rectangle" dans la barre d'outils, ajuster les dimensions dans le panneau de configuration
2. **Pièce irrégulière** : Cliquer sur "Irrégulier", placer les points sur le canevas, double-cliquer pour fermer le polygone

### Ajouter des meubles

1. Sélectionner le type de meuble dans la barre d'outils (avec ou sans drain)
2. Le meuble apparaît au centre de la pièce avec des dimensions par défaut
3. Ajuster la position et la taille via le panneau de configuration
4. Utiliser les touches directionnelles ou le glisser-déposer pour déplacer

### Générer le chemin de câbles

1. Configurer les zones restreintes et le placement des meubles
2. Cliquer sur "Générer le chemin de câbles"
3. L'algorithme calcule automatiquement le chemin optimal en contournant les obstacles
4. Ajuster l'espacement et le motif des câbles si nécessaire

### Raccourcis clavier

- `Retour arrière / Suppr` : Supprimer le meuble sélectionné
- `Ctrl+Z` : Annuler
- `Ctrl+Y` : Rétablir
- `Ctrl+S` : Sauvegarder le projet
- `Ctrl+N` : Nouveau projet

## 🏗️ Architecture

Ce projet suit l'**Architecture Hexagonale** (Ports et Adaptateurs) :

- **Couche Domaine** : Logique métier (génération de chemins, contraintes, géométrie)
- **Couche GUI** : Interface utilisateur Swing
- **Couche Infrastructure** : Persistance fichier

**Patrons de conception utilisés :**
- **Mémento** (Annuler/Rétablir)
- **Contrôleur Larman** (séparation Contrôleur/Vue)
- **Stratégie** (algorithmes de génération de chemins)

## 👨‍💻 Mes contributions

- Conception de l'architecture (trois couches : Domaine, UI, Infrastructure)
- Design UI avec Figma
- Algorithme de génération du chemin de câbles
- Algorithme de génération de la membrane chauffante
- Rendu des meubles et objets dans la pièce
- Annuler / Rétablir (patron Mémento)
- Position de la souris dans le canevas

## 👥 Contributeurs

Ce projet a été développé par :

- **[Petiton Wiseley Paul-Enzer](https://github.com/pwiseley)**
- **[Wily Roussel Tatow Doungmo](https://github.com/witly2)**
- **[Ouedraogo Aliya Imann](https://github.com/aioue8)**
- **[Kémila Bakary](https://github.com/kemilabakary)**
- **[Dongmeza Murielle Christelle](https://github.com/muriellec)**

## 📝 Licence

© 2025 Équipe 23. Tous droits réservés.

Ce projet a été développé dans le cadre des cours IFT-2007/GLO-2004 à l'Université Laval.

---

**Note** : Cette application a été conçue à des fins éducatives dans le cadre du programme de génie logiciel.
