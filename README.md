# Documentation de l'API SuperApp

## Introduction
L'API SuperApp fournit des fonctionnalités avancées pour interagir avec notre application SuperApp. Cette API vous permet d'accéder à des fonctionnalités telles que la gestion des utilisateurs, la création et la récupération de données, ainsi que la personnalisation de l'expérience utilisateur.

## Authentification
Toutes les requêtes vers l'API SuperApp doivent être authentifiées à l'aide de la méthode d'authentification suivante :

- Endpoint : `/auth`
- Méthode : `POST`
- Paramètres :
  - `username` (obligatoire) : le nom d'utilisateur de l'utilisateur
  - `password` (obligatoire) : le mot de passe de l'utilisateur

Exemple de requête cURL :
curl -X POST -d "username=johndoe&password=mypassword" https://api.superapp.com/auth


Exemple de réponse :
```json
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6ImpvaG5kb2UiLCJpYXQiOjE2MjExMzE1NzAsImV4cCI6MTYyMTEzMjE3MH0.IKOSZFG6qDdfN_3Yq09iXMkPfDwA1jUvDz-0QI_2Sv0"
}

Utilisez le jeton d'accès retourné dans les réponses pour authentifier les requêtes ultérieures en l'incluant dans l'en-tête Authorization comme suit :
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6ImpvaG5kb2UiLCJpYXQiOjE2MjExMzE1NzAsImV4cCI6MTYyMTEzMjE3MH0.IKOSZFG6qDdfN_3Yq09iXMkPfDwA1jUvDz-0QI_2Sv0

Récupérer les informations utilisateur
Pour récupérer les informations d'un utilisateur spécifique, utilisez l'endpoint suivant :

Endpoint : /users/{userId}
Méthode : GET
Paramètres :
userId (obligatoire) : l'identifiant de l'utilisateur
Exemple de requête cURL :

curl -X GET -H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6ImpvaG5kb2UiLCJpYXQiOjE2MjExMzE1NzAsImV4cCI6MTYyMTEzMjE3MH0.IKOSZFG6qDdfN_3Yq09iXMkPfDwA1jUvDz-0QI_2Sv0" https://api.superapp.com/users/123
