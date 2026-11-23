# Outils pour les intervenants, sur GitHub Pages

Dossier prêt à déposer sur GitHub (décision de l'enseignant du 21/11/2026, qui remplace la Forge). **Rien n'a été publié** : le dépôt se fait avec votre compte GitHub.

```
docs/
  index.html            page d'accueil pour les intervenants (deux boutons)
  escape-game/          l'escape game v9.2 (page de la variante « élève » + la vidéo)
  simulateur/           le simulateur de prise de vue « Du réglage à l'EXIF » v2.3-rc4
  robots.txt            demande aux moteurs de recherche de ne pas indexer
  .nojekyll             publier les fichiers tels quels, sans traitement Jekyll
```

Les pages sont autonomes (aucune ressource externe chargée, chemins relatifs), sauf la carte de la mission 6 (OpenStreetMap) qui demande Internet. Le dossier fait environ 18 Mo (aucun fichier proche de la limite de 100 Mo de GitHub).

## Point important : GitHub Pages et l'accès limité

À ma connaissance (à vérifier dans la documentation GitHub et vos réglages) :
- avec un compte **gratuit**, GitHub Pages ne publie que des dépôts **publics** ;
- le site publié est lisible par **toute personne qui a l'adresse** : GitHub ne permet de réserver un site à des invités que dans certaines offres payantes (Enterprise Cloud).

Conséquence : le choix « accès limité » du 21/11 n'est **pas tenable** avec un compte gratuit. Ce que l'on peut faire : une adresse non listée (aucun lien public, `robots.txt` et page d'accueil en `noindex`), mais qui n'est pas secrète. Si l'accès doit rester limité, deux repères : envoyer directement `EscapeGame_photon-pixel_v9_1_enseignant.zip` et le simulateur par l'ENT ou courriel, ou publier seulement l'un des deux outils.

Ce que la publication rend lisible par tous :
- les photos de la mission 6, avec leurs métadonnées d'origine, **position GPS comprise** (l'activité consiste à les lire) ;
- le jeu complet, élèves compris (à la maison) ;
- la **photo d'un enfant** du simulateur : vérifier sa licence avant de publier.

## Déposer sur GitHub

1. Créer un dépôt **vide** sur GitHub (par exemple `snt-intervenants-photographie`), sans README, sans licence automatique. Pour Pages avec un compte gratuit, il doit être **public**.
2. Dans ce dossier (PowerShell) :

```powershell
git init -b main
git config core.autocrlf false
git config user.name "<nom affiché sur GitHub>"
git config user.email "<adresse noreply GitHub>"
git add .
git commit -m "Escape game v7 et simulateur pour les intervenants"
git remote add origin https://github.com/<votre-compte>/<depot>.git
git push -u origin main
```

3. Sur GitHub : **Settings, Pages**, source **Deploy from a branch**, branche `main`, dossier **/docs**, puis enregistrer.
4. Après une à deux minutes, l'adresse apparaît en haut de la page Pages : `https://<votre-compte>.github.io/<depot>/`.
5. Envoyer cette adresse au photographe et à la documentaliste.

## Compte GitHub

L'adresse courriel d'un commit est **publique** sur un dépôt public. Utilisez l'adresse « noreply » de GitHub (Settings, Emails, « Keep my email addresses private », qui affiche une adresse du type `<numéro>+<compte>@users.noreply.github.com`) dans la commande `git config user.email` ci-dessus, pas votre adresse académique ni personnelle. Aucune identité n'est configurée sur ce poste : `git commit` refusera tant que ces deux lignes ne sont pas faites.

C'est un service extérieur à l'Éducation nationale, sur un compte personnel : n'y déposer aucune donnée d'élève (ce dossier n'en contient pas : la progression d'un élève reste dans son navigateur).

## Mettre à jour

Remplacer le fichier concerné dans `docs/`, puis `git add .`, `git commit`, `git push` : le site se met à jour.

## Non vérifié

- Aucun dépôt n'a été créé ni poussé ; la page Pages n'a pas été vue en ligne.
- En essai local (serveur Python, Edge, sous-dossier), l'accueil, l'escape game (8 missions, vidéo chargée) et le simulateur s'ouvrent sans erreur. Ce test portait sur l'ancien nom de dossier `public/` (contenu identique, renommé `docs/`).
- Le simulateur est en version v2.3-rc4, **jamais essayé en classe** (déroulé SEQ02, §1).
