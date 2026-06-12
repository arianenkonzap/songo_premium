# Songo – Version Distante (Ajax + Flask)

## Structure du projet

```
songo_distant/
├── app.py               ← Serveur Flask (API REST)
├── requirements.txt     ← Dépendances Python
└── templates/
    └── index.html       ← Interface cliente (HTML + CSS + Ajax)
```

## Installation et lancement

```bash
# 1. Installer les dépendances
pip install -r requirements.txt

# 2. Lancer le serveur
python app.py
```

Le serveur démarre sur http://localhost:5000

## Comment jouer à deux machines

1. Lancer le serveur sur une machine accessible sur le réseau local
2. **Joueur 1** : ouvrir http://<IP_SERVEUR>:5000 → cliquer "Créer une nouvelle partie"
3. **Joueur 2** : ouvrir http://<IP_SERVEUR>:5000 → entrer le code de partie → cliquer "Rejoindre"

## API REST

| Méthode | Route                  | Description                        |
|---------|------------------------|------------------------------------|
| POST    | /api/creer             | Crée une partie, retourne game_id  |
| POST    | /api/rejoindre/:id     | Rejoindre une partie existante     |
| GET     | /api/etat/:id          | Récupérer l'état actuel (polling)  |
| POST    | /api/jouer/:id         | Jouer un coup                      |
