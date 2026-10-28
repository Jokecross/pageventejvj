# Page de vente — Jean Val Jean (JVJ), formation IA

Page de vente de Jean Val Jean (@jean_val_jean06, TikTok). Un seul objectif : le
formulaire. Un setter rappelle le lead dans les 10 minutes, puis lui ouvre l'espace membre.

Fichier HTML unique (CSS et JS dans la page, sans build). La logique vient de la page
Marcus (`~/page de vente Marcus`, elle-même reprise de Mexed et de Gaspard), aucune de
ces pages n'a été modifiée. Le design est entièrement nouveau (DA « Nuit 2 étoiles »).

```
index.html        la page
img/              image de partage + portraits de JVJ (à déposer)
favicon.svg       la couronne
vercel.json       URLs propres, liens courts /nom, noindex
A-COMPLETER.md    tout ce qui attend un contenu réel
```

## En local

```
python3 -m http.server 8095
```

puis http://localhost:8095. Les liens courts `/jvj` ne marchent qu'une fois sur Vercel
(utiliser `?ref=jvj` en local).

## Comment circule un lead

```
Tous les boutons « JE VEUX COMMENCER »  →  modale du formulaire (la page ne défile pas)
        │  POST /rest/v1/leads avec la clé anon
        ▼
Table public.leads (schéma des templates)  →  setters
        │
        └──►  dans la modale, le formulaire laisse la place à « C'est envoyé. »
              + Lead (Meta) / SubmitForm (TikTok) si les pixels sont renseignés
```

- Téléphone au format E.164, +33 par défaut.
- **Suivi** : `?ref=jvj` (ou `?src=jvj`, ou `/jvj`) et les UTM sont retenus 30 jours
  dans le navigateur et remplis dans des champs cachés. Sans colonnes dédiées
  (`COLONNES_SUIVI = false`), `ref` part dans `source` et les UTM dans `page_url`.
  Compter les leads de JVJ = filtrer `source = 'jvj'`.
- **Client / offre** : `CLIENT_OFFRE = true` envoie `client = 'JVJ'` et
  `offre = 'JVJ — Formation IA'` (colonnes à créer d'abord, voir A-COMPLETER.md).
- **Anti-spam** : champ leurre `company` ; rempli, la page simule un succès sans rien envoyer.

## Les photos

Déposer les WebP sous ces noms exacts, la page les affiche toute seule (sinon fond neutre) :

| Fichier | Où | Format conseillé |
|---|---|---|
| `img/jvj-profil.webp` | pastille de profil du hero + signature de la lettre | carré, 256 × 256 |
| `img/jvj-question.webp` | carte « Mais tu fais quoi, en vrai ? » | portrait 4:5, 1000 × 1250 |
| `img/jvj-moi.webp` | section « Qui je suis » | portrait 4:5, 1000 × 1250 |

Conversion : `ffmpeg -i photo.jpg -vf "scale=1000:-2" -quality 80 img/jvj-moi.webp`.
Les originaux vont dans `photos-brutes/` (hors git).

## Charte « Nuit 2 étoiles »

| Rôle | Valeur |
|---|---|
| Fond / fond de section | `#0B0B0C` / `#141416` |
| Texte / secondaire | `#F5F2EA` / `#A8A6A0` |
| Accent unique | or `#E3B64F` (mot clé des titres, boutons, couronne, numéros) |
| Lignes | 1 px, blanc à 8 % |
| Titres | Inter Tight 600–700, interlettrage −2,5 % |
| Mot clé | Instrument Serif italique, or |
| Texte | Inter 400–500, 17–18 px ; surtitres 12 px capitales espacées |
| Boutons | fond or, texte noir en capitales, rayon 8 px, sans ombre |

## Structure (celle de nos pages Mexed / Maxence / Marcus)

Bandeau or → hero (profil, badge « Nouveau », titre avec « L’IA. » en aplat or, puces,
VSL encadrée, CTA) → 3 chiffres → carte « La question » (lettre signée) → carte d'offre
« Ce que tu reçois » (Inclus + « moins cher qu’un resto ») → bandeau qui défile →
parcours en 4 étapes sur un rail qui se remplit → pour qui →
3 étapes → qui je suis → FAQ en cartes → carte finale → pied de page.
Formulaire en modale (`#formulaire` dans l'adresse l'ouvre à l'arrivée).

Animations : fondu à l’apparition, rail du parcours qui se remplit,
bandeau qui défile ; tout est coupé si le téléphone demande moins d'animations.
Mobile d'abord, testé à 375 px. La barre fixe en bas apparaît une fois le bouton du
hero dépassé, se cache sur la carte finale et quand la modale est ouverte, et n'existe
pas au-delà de 980 px.
