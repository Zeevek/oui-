# 💍 ZeQuizz — la demande

Un petit quiz romantique, personnalisé, à répondre sur téléphone ou ordinateur.
À chaque bonne réponse, la scène se réchauffe (dégradé crépuscule → aube) ; une
fois toutes les questions passées, l'écran final dévoile la demande, une pluie de
cœurs, et un lien vers les documents officiels.

Application **hors-ligne**, **sans dépendance** (aucun CDN), en **un seul fichier**
`index.html`. Prête pour GitHub Pages.

---

## ✏️ Personnaliser

Tout se règle dans le bloc `CONFIG`, en haut de la balise `<script>` du fichier
`index.html`. Rien d'autre à toucher.

| Champ | Rôle |
|---|---|
| `prenom` | Le prénom (ou surnom) affiché dans l'intro. |
| `introTitre` / `introTexte` | Le message d'accueil. |
| `questions[]` | La liste des questions. |
| `propositions` | Les choix proposés pour une question. |
| `bonneReponse` | Index de la bonne réponse : `0` = 1re proposition, `1` = 2e, etc. |
| `indice` | Petit mot affiché en cas d'erreur (facultatif, mettre `""` pour rien). |
| `reessayerJusquauBonneReponse` | `true` : elle doit trouver la bonne réponse pour avancer (aucun échec possible). `false` : une erreur fait passer à la suite quand même. |
| `finTitre` / `finTexte` / `boutonOui` | L'écran de la demande. |
| `ouiTitre` / `ouiTexte` / `boutonDocs` | L'écran après le « oui ». |
| `boutonLien` | L'adresse ouverte à la fin. Par défaut : la page PACS de service-public.fr. |

### Documents officiels du PACS
- Page complète (procédure + formulaires) : `https://www.service-public.fr/particuliers/vosdroits/N144`
- Déclaration conjointe (Cerfa 15725) : `https://www.formulaires.service-public.gouv.fr/gf/cerfa_15725.do`
- Convention type (Cerfa 15726) : `https://www.formulaires.service-public.gouv.fr/gf/cerfa_15726.do`

---

## 🔒 Confidentialité — à lire avant de publier

Le fichier contient des messages personnels (surnoms, blagues, la demande).

- Un site **GitHub Pages est toujours public** : toute personne ayant l'URL peut
  ouvrir la page **et** en voir le code source.
- Sur un **compte gratuit**, GitHub Pages ne fonctionne **que depuis un dépôt public**
  (le code apparaît alors sur ton profil et devient indexable).
- Pour publier depuis un dépôt **privé**, il faut **GitHub Pro** (le code reste caché,
  seule la page reste publique via son URL).

**Le plus simple pour une surprise :** l'appli étant autonome, tu peux aussi juste
lui **envoyer le fichier** ou l'**ouvrir toi-même** devant elle — sans rien héberger.

---

## 🚀 Déploiement GitHub Pages

1. Crée un dépôt sur GitHub (nom discret conseillé si public).
2. Pousse ce dossier (voir commandes ci-dessous).
3. Dans **Settings → Pages**, choisis la branche `main` et le dossier `/ (root)`.
4. L'URL sera de la forme `https://zeevek.github.io/<nom-du-depot>/`.

---

## ✅ Validation

Le JavaScript embarqué est vérifié avec :

```bash
node --check <(sed -n '/<script>/,/<\/script>/p' index.html | sed '1d;$d')
```

---

*Projet personnel — tous droits réservés.*
