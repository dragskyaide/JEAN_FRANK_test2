# Configuration sécurisée — JEAN FRANK

- Ne pas publier `google-services.json` Android ni aucun fichier `.env` dans le site Web.
- Les clés Firebase Web sont des identifiants de configuration, mais doivent être protégées par restrictions de domaine, App Check et règles Firestore strictes.
- La clé OpenAI doit rester uniquement dans un backend HTTPS. Le navigateur appelle ce backend avec un jeton utilisateur vérifié et des limites de débit.
- Les droits premium doivent être vérifiés côté serveur/Firestore, jamais par une simple variable JavaScript.
- Les paiements doivent être confirmés par webhook fournisseur côté serveur avant activation des droits.
- Les opérations admin exigent des rôles vérifiés côté serveur et journalisation d'audit.
