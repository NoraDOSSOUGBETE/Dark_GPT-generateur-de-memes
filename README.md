#  Dark-GPT — Générateur de Mèmes IA 

> *Transforme n'importe quelle situation en mème viral, avec une touche de philosophie absurde made in Côte d'Ivoire.*

[![Streamlit App](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)](https://streamlit.io)
[![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python)](https://python.org)
[![Gemini](https://img.shields.io/badge/Powered%20by-Gemini%202.0%20Flash-orange?logo=google)](https://deepmind.google/technologies/gemini/)
[![LangChain](https://img.shields.io/badge/LangChain-🦜-green)](https://langchain.com)

---

##  C'est quoi Dark-GPT ?

Dark-GPT est une application Streamlit qui prend une **situation du quotidien** en entrée et génère automatiquement un **mème viral** adapté, avec un texte drôle, percutant, et teinté d'humour ivoirien.

L'IA choisit parmi **19 templates de mèmes classiques** (Drake, Gru's Plan, Distracted Boyfriend, etc.), génère les textes appropriés, et affiche le tout sous forme d'image annotée directement dans le chat.

### Exemple

>  *"Quand tu réalises que tu as un examen demain et que tu n'as pas révisé"*

→ L'IA choisit le template `two_buttons`, génère deux options absurdes mais hilarantes, et affiche le mème final !

---

##  Stack technique

| Composant | Technologie |
|---|---|
| Interface | [Streamlit](https://streamlit.io) |
| LLM | [Gemini 2.0 Flash](https://deepmind.google) via LangChain |
| Orchestration | [LangChain](https://langchain.com) (`ChatPromptTemplate`, structured output) |
| Templates de mèmes | 19 templates intégrés (imgflip) |
| Positionnement du texte | HTML/CSS inline via `st.markdown` |

---

##  Lancer le projet en local

### 1. Cloner le repo

```bash
git clone https://github.com/ton-username/dark-gpt.git
cd dark-gpt
```

### 2. Installer les dépendances

```bash
pip install -r requirements.txt
```

### 3. Configurer la clé API

Crée un fichier `.streamlit/secrets.toml` à la racine du projet :

```toml
GOOGLE_API_KEY = "ta-clé-api-google-ici"
```

>  Obtiens une clé gratuite sur [Google AI Studio](https://aistudio.google.com/app/apikey)

### 4. Lancer l'application

```bash
streamlit run streamlit_app.py
```

---

## 📁 Structure du projet

```
dark-gpt/
├── streamlit_app.py       # Point d'entrée — interface chat Streamlit
├── response.py            # Logique IA : génération du mème + rendu HTML
├── template.py            # Catalogue des 19 templates de mèmes
├── Template_class.py      # Classe Pydantic pour le structured output LangChain
├── positions.py           # Coordonnées de positionnement du texte par mème
├── Exemples.py            # Exemples few-shot injectés dans le prompt
├── requirements.txt       # Dépendances Python
└── .streamlit/
    └── secrets.toml       # Clé API (à créer localement, non versionnée)
```

---

##  Templates de mèmes disponibles

| ID | Mème |
|---|---|
| `two_buttons` | Two Buttons |
| `drake_bling` | Drake Hotline Bling |
| `batman_slapping_robin` | Batman Slapping Robin |
| `woman_yelling_at_cat` | Woman Yelling At Cat |
| `distracted_boyfriend` | Distracted Boyfriend |
| `gru_plan` | Gru's Plan |
| `trump_bill_signing` | Trump Bill Signing |
| `waiting_skeleton` | Waiting Skeleton |
| `clown_applying_makeup` | Clown Applying Makeup |
| `bernie_sanders_once_again` | Bernie Sanders Once Again Asking |
| `hide_the_pain_harold` | Hide the Pain Harold |
| `monkey_puppet` | Monkey Puppet |
| `x_x_everywhere` | X, X Everywhere |
| `tuxedo_winnie_the_pooh` | Tuxedo Winnie The Pooh |
| `yall_got_any_more_of_that` | Y'all Got Any More Of That |
| `i_bet_hes_thinking_about_other_women` | I Bet He's Thinking... |
| `disaster_girl` | Disaster Girl |
| `left_exit_12_off_ramp` | Left Exit 12 Off Ramp |
| `expanding_brain` | Expanding Brain |

---

##  Comment ça marche ?

```
Situation (texte libre)
        │
        ▼
  Prompt LangChain
  (19 templates + exemples few-shot ivoiriens)
        │
        ▼
  Gemini 2.0 Flash
  (structured output → classe Template)
        │
        ▼
  Sélection du template + génération des textes
        │
        ▼
  Rendu HTML/CSS inline sur l'image du mème
        │
        ▼
  Affichage dans le chat Streamlit 🎉
```

---

##  L'IA ivoirienne

Le prompt système a une personnalité unique : une **IA ivoirienne de haut niveau** qui donne des conseils absurdes mais philosophiquement solides, mêlant expressions locales et logique décalée. Chaque réponse doit faire sourire… mais au fond, donner raison à l'IA.

---


## 📄 Licence

Ce projet est sous licence [LGPL-2.1](./LICENSE).

---

<p align="center">Fait avec ❤️ et un peu de folie ivoirienne 🇨🇮</p>
