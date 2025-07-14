# Projet Analyse de Sentiment Vocal

![Python](https://img.shields.io/badge/Python-3.10-blue.svg)

## Description du Projet

L’**API d’Analyse de Sentiment Vocal** est un projet innovant qui transforme la parole en texte, puis analyse ce texte pour en détecter le **sentiment** exprimé. Elle combine reconnaissance vocale et traitement du langage naturel pour fournir une évaluation émotionnelle du discours de l’utilisateur.

### Fonctionnalités Clés

* 🎙️ **Conversion Parole en Texte** : Utilisation de modèles préentraînés pour la transcription audio.
* 💬 **Analyse de Sentiment** : Détection du ton émotionnel du texte transcrit (positif, négatif, neutre).
* 🔗 **API REST** : Utilisable comme service API, facilement intégrable dans d'autres applications.

---

## Modèles Utilisés

Voici les modèles préentraînés utilisés dans cette API :

| Composant                  | Modèle                                                                                                                        | Description                                                                                                                                                     |
| -------------------------- | ----------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Reconnaissance vocale (FR) | [`jonatasgrosman/wav2vec2-large-xlsr-53-french`](https://huggingface.co/jonatasgrosman/wav2vec2-large-xlsr-53-french)         | Modèle Wav2Vec2 finement ajusté pour la transcription vocale en **français**. Haute précision pour les entrées audio francophones.                              |
| Reconnaissance vocale (EN) | [`facebook/wav2vec2-large-960h-lv60-self`](https://huggingface.co/facebook/wav2vec2-large-960h-lv60-self)                     | Modèle de base de Facebook pour la reconnaissance vocale en **anglais**. Utilisé si la langue détectée n'est pas le français.                                   |
| Analyse de sentiment       | [`nlptown/bert-base-multilingual-uncased-sentiment`](https://huggingface.co/nlptown/bert-base-multilingual-uncased-sentiment) | Modèle BERT multilingue pour l’analyse des sentiments. Capable de traiter plusieurs langues (dont le français et l’anglais). Renvoie un score de 1 à 5 étoiles. |

---

## Pile Technologique

| Technologie                                                  | Description                                                 |
| ------------------------------------------------------------ | ----------------------------------------------------------- |
| ![Python](https://img.shields.io/badge/Python-3.10-blue.svg) | Langage utilisé pour le développement du backend.           |
| Hugging Face Transformers                                    | Pour le chargement et l’utilisation des modèles NLP et ASR. |
| Gradio                                                       | Interface utilisateur pour tester l’API vocalement.         |

---

## Installation

### Prérequis

* Python 3.10 ou version supérieure

### Guide Pas à Pas

1. **Cloner le dépôt** :

   ```bash
   git clone https://github.com/Mvhamad/Sentiment-Analysis-Voice-APII.git
   cd Sentiment-Analysis-Voice-APII
   ```

2. **Installer les dépendances** :

   ```bash
   pip install -r requirements.txt
   ```

3. **Configurer les variables d’environnement** (si nécessaire) :

   * Créez un fichier `.env` à la racine du projet pour stocker les clés API ou chemins personnalisés si requis.

---

## Utilisation

Pour démarrer l’API :

```bash
python src/api/main.py
```

### Exemple de Requête

Envoyez une requête POST avec un fichier audio (`.wav`, `.mp3`, etc.) vers l’endpoint prévu. Le serveur renverra :

* la **transcription du discours**
* et son **analyse de sentiment** (par exemple : *positif*, *neutre*, *négatif*).

---

## Structure du Projet

```
Sentiment-Analysis-Voice-APII/
├── src/
│   ├── api/                    # Point d’entrée de l’API
│   │   └── main.py
│   ├── interface/              # Interface Gradio
│   │   └── gradio_app.py
│   └── models/                 # Logique et traitement
│       ├── pipeline.py
│       ├── sentiment_analyzer.py
│       └── speech_to_text.py
├── .gitignore
└── requirements.txt
```

---

## Contribution

Les contributions sont les bienvenues pour améliorer les performances ou ajouter de nouvelles fonctionnalités :

1. Forkez le projet
2. Créez une branche : `feature/ma-fonctionnalité`
3. Commitez vos modifications
4. Ouvrez une Pull Request 🧠
