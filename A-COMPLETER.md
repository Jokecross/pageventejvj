# À compléter — Jean Val Jean, formation IA

Tout se règle dans le bloc `CONFIGURATION` en bas de `index.html`, sauf mention contraire.
Pour tout retrouver : `grep -n "À COMPLÉTER\|À FOURNIR" index.html`

| Quoi | Où | État |
|---|---|---|
| VSL | `videos/vsl-jvj.mp4` (depuis « JEAN VSL V2 .mov », 4K → 720p H.264) + affiche `img/vsl-affiche.webp` | **faite le 01/11** : démarre seule sans le son, pas de pause ni d'avance, un appui = son + reprise du début, fin = bouton vers le formulaire. Pour la changer : nouveau nom de fichier (cache 7 j) |
| Photos de JVJ | `img/jvj-profil.webp` (bateau, entière comme sur TikTok), `img/jvj-question.webp` (canapé), `img/jvj-moi.webp` (voiture, cigare) ; originaux dans `photos-brutes/` | **faites le 28/10** ; ⚠️ voiture + cigare et montre + bière : contraires au premier brief (« pas de voitures, pas de montres »), gardées sur choix de Martin |
| Base des leads | projet Supabase de Sirius (`mmpazpnzkmianenkfyiv`), équipe Base44, `offre = jvj` | **branchée le 03/11** ; nécessite `CRM Sirius/supabase/05-offre-jvj.sql` |
| Pixel Meta | `PIXELS.meta` (PageView + Lead à l'envoi) | à fournir |
| Pixel TikTok | `PIXELS.tiktok` (page + SubmitForm à l'envoi) | à fournir |
| E-mail de contact | `CONTACT_EMAIL` | fait (Mainjf@hotmail.com) |
| Mentions légales, Politique de confidentialité, CGV | `LIENS` → /legal (legal.html, MansasMogules L.L.C-FZ) | fait le 08/11 |
| Parcours de JVJ | section H, balise `<p class="parcours">` (masquée tant qu'elle est vide) | à écrire avec lui |
| Image de partage | `og:image` dans `<head>` | fait : https://www.jvj-starter.com/img/partage.png |
| Indexation Google | `<meta name="robots" content="noindex">` + `X-Robots-Tag` dans `vercel.json` | noindex par défaut |

## Textes à valider

- **Hero (28/10, à la demande de Martin : « pas assez compréhensible »)** : accroche « Pas de trading, pas de casino. »,
  titre « Génère tes premiers euros grâce à l’IA. », sous-titre « Sans compétences et sans savoir coder. »
  (remplace le titre du brief « Pas de trading. Pas de casino. L’IA. »). Surtitre « Vous êtes des milliers… », puces et phrase
  « Les outils, les méthodes et les scripts sont fournis… » retirés par Martin.

- **Section « Ce que tu vas apprendre »** : commentaire `<!-- Contenu à valider avec JVJ -->` dans le code,
  y compris les pastilles « Tu repars avec : tes outils IA / ta méthode / tes scripts / ton plan ».
- **Ajouts (tirés du brief, aucun chiffre inventé)** : bandeau du haut, badge « Nouveau · Formation IA »,
  chiffres « +140K / 7 jours / 24h/24 »,
  « Tout est inclus », bandeau qui défile, titre « Trois étapes, c’est tout. », « C’est pour toi ? »,
  « Tes questions », sous-titre de la modale « Sur ton numéro ou sur WhatsApp. », pastilles de bio
  « No Trading / No Casino / J’ai choisi la vie 2 star ».
- **Abonnés** : « +140K » d'après le brief (plus de 140 000). Pas de badge « vérifié » : à ajouter seulement si son compte l'est.
- **Écarts assumés avec le premier brief**, à la demande de Martin (structure de nos autres pages) :
  formulaire en modale, cartes, bandeau qui défile, lueur dorée discrète sous la vidéo et la carte finale.
