# Test
Test

import sys                      # Permet de configurer les chemins des imports
from pathlib import Path        # Permet de manipuler les chemins de fichiers

project_root = Path.cwd()       # Récupère le dossier de travail de Jupyter

if not (project_root / "scripts").is_dir():  # Si on n'est pas déjà à la racine
    project_root = project_root.parent.parent  # Remonte depuis notebooks/fine_tuning

assert (project_root / "scripts").is_dir(), "Vérifie le dossier de travail."

if str(project_root) not in sys.path:       # Évite d'ajouter deux fois le chemin
    sys.path.insert(0, str(project_root))   # Rend les scripts du projet importables

print("Racine du projet :", project_root)  # Affiche le chemin trouvé
