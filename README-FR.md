# JEAN FRANK — Académie internationale de jeu de dames 10×10

**Version de travail Web v0.3.0** — PWA indépendante du dépôt GitHub actuellement publié.

Cette application concerne exclusivement le **jeu de dames international 10×10 (règles FMJD)**. Ce n'est pas une application d'échecs.

## Contenu de cette version

- Interface Web responsive et installable (PWA).
- Damier international 10×10 avec numérotation FMJD des 50 cases jouables.
- Moteur JavaScript adapté du `JeanFrankRulesEngine.kt` de l'archive Android.
- Déplacements légaux des pions et dames, prises en avant/arrière, prises obligatoires, prise majoritaire, rafles, dames volantes, promotion différée pendant une rafle et notation FMJD.
- Suivi des répétitions de position et compteur de 25 coups de dames sans prise pour rendre la nulle réclamable, conformément à la logique de référence Kotlin.
- Actions locales : nouvelle partie, annulation, réclamation de nulle, accord de nulle et abandon.
- 10 modules gratuits et 50 leçons converties depuis `FreeCurriculumData.kt`.
- Salle d'exercices : 10 exercices issus du catalogue natif, avec solutions rejouées automatiquement par le moteur Web, indices et explications.
- Bibliothèque des PDF fournis dans l'archive source. Les droits de diffusion doivent être vérifiés avant publication publique.

## Tests exécutés

Commande : `npm test`

**19 tests réussis, 0 échec** lors de la génération de cette version. La batterie couvre notamment :

- correspondance des cases 1 à 50 ;
- position initiale (20 pions par camp, 9 coups légaux) ;
- prise des pions vers l'avant et l'arrière ;
- prise obligatoire et prise majoritaire ;
- promotion après la fin d'une rafle ;
- dames volantes et cases d'atterrissage ;
- non-répétition d'une prise déjà effectuée pendant une rafle ;
- répétition triple, 25 coups de dame sans prise ;
- abandon, accord de nulle et notation ;
- chemins de solution des 10 exercices.

Ces tests automatisés ne remplacent pas encore une certification indépendante FMJD ni une comparaison exhaustive de toutes les positions du moteur Kotlin. La version reste une version de validation.

## Lancer en local

Depuis ce dossier :

```bash
python -m http.server 8000
```

Ouvrir ensuite `http://localhost:8000`. Pour installer la PWA, utiliser HTTPS ou localhost et un navigateur compatible.

## Fonctions qui ne sont pas encore activées

- Professeur IA OpenAI : nécessite une API serveur HTTPS ; la clé privée ne doit jamais être placée dans le navigateur.
- Comptes, authentification, synchronisation et sauvegarde cloud : Firebase Web doit être configuré et testé.
- Abonnements et paiements : aucun paiement réel n'est activé ; les tarifs affichés sont des références issues du projet source.
- IA de jeu et analyse avancée : le moteur de recherche Kotlin doit être porté vers Web Worker et validé.
- Administration : les rôles et opérations privilégiées nécessitent un backend sécurisé.
- Les thèmes avancés sont catalogués ; ils ne représentent pas 5 000 leçons originales déjà rédigées.

## Sécurité et publication

Consulter `CONFIGURATION-SECURITE.md`. Ne jamais publier de clé OpenAI privée, de secret Firebase ou de fichier `.env` contenant des secrets. Les contenus payants et les droits d'accès doivent être contrôlés côté serveur. Ne pas remplacer l'application GitHub actuelle avant les essais et la validation de cette reconstruction.
