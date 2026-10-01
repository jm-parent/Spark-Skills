# Spark-Skills

Skills d'agent pour TeamSpark.

## spark-gen : mode opératoire

Génère le livrable TeamSpark d'un projet (`project.md`, vidéo, logo, visuels) à partir de son dépôt.

**Prérequis** : Node.js installé, et un agent compatible avec les skills (GitHub Copilot dans VS Code, par exemple).

### 1. Installer le skill (une seule fois)

```
npx skills add jm-parent/Spark-Skills --skill spark-gen -g
```

Acceptez les choix par défaut, puis rechargez les skills ou redémarrez VS Code.

### 2. Générer le livrable

1. Ouvrez le dépôt du projet à présenter dans VS Code.
2. Dans l'agent, lancez `/spark-gen`.
3. Indiquez la durée de la vidéo, entre 20 et 120 secondes (20 par défaut).
4. Attendez la fin de la génération. Le skill peut installer lui-même `/brag` et Hyperframes si besoin.

Il crée uniquement `_spotlight/<nom-du-projet>/` et ne modifie aucun fichier existant. Ce dossier contient :

- `project.md` : titre, description, équipe, lien, durée
- `brag.mp4` : la vidéo
- le logo et les visuels, s'ils existent dans le dépôt

### 3. Relire le récapitulatif

Le skill affiche le contenu de `project.md` et les champs omis faute d'information. Vérifiez que la description et l'équipe sont corrects. Vous pouvez corriger `project.md` à la main.

### 4. Envoyer le livrable

1. Récupérez le dossier `_spotlight/<nom-du-projet>/`, ou l'archive `_spotlight/<nom-du-projet>.zip` créée par le skill.
2. Envoyez-le à **Jean-Marie PARENT** (Teams ou mail).
3. Une fois ajouté à TeamSpark, votre projet apparaît dans la boucle de l'écran d'équipe.

## En cas de problème

- **La commande `/spark-gen` n'apparaît pas** : rechargez les skills ou redémarrez VS Code.
- **La vidéo n'a pas pu être générée** : le skill l'indique et livre la fiche sans vidéo, avec l'erreur rencontrée. Envoyez quand même le dossier.
- **Fichier trop gros** : la vidéo est limitée à 20 Mo, et le skill la réencode si nécessaire.

