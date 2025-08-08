
<h1 style="font-size: 48px">Keycloak</h1>
___
# Sommaire 

- [[#Intro]]
- [[#Fonctionnalités]]
- [[#Core Concepts]]
- [[#Tokens]]
- [[#Authentification]]
- [[#Gestion des Identités]]
- [[#Conclusion]]

___
# Intro

	Sécurité des données et gestion des identités -> enjeux majeurs des apps modernes.  
	Keycloak (Red Hat) : solution open-source IAM centralisée.  
	Auth, autorisation, SSO, protocoles standards (OAuth2, OIDC, SAML).

___
# Fonctionnalités

1) SSO
	*-> Un seul id pour toutes les apps*
2) Autorisations
	*-> Définir les authorisations selon les rôles*
3) Normes de Sécurité
	*(OpenID Connect, OAuth 2.0, SAML) -> protocoles robustes*

___


![[Core_Concepts_Keycloak.webp]]

___
# Core Concepts

1) Realm :
	 *Définit les clients, utilisateurs, rôles; ***Realms par defaut = "master"
2) Client :
	*Application client (ID, Url, flux d'auth)
3) Utilisateur :
	*Utilisateur Keycloak (ID, username, email, rôle, group, realm)*
4) Rôle
	*Admin, User -> Permissions*
5) Groupe
	*-> Regrouper les utilisateur et attribuer les rôle*
6) Consentement
	*Accès aux données utilisateur*

___
# Tokens

1) Access Token
	*Jeton d'authentification Keycloak, intégré à l'entête de la requête (info utilisateur, permissions)*
2) Identity Token
	*(nom, mail, mdp utilisateur) ->prouver l'identité*
3) Refresh Token
	*-> Renouveler les accès sans se réauthentifier*
4) Offline Session Token
	*-> Garde la session active, même après la fermeture du navigateur*

___
# Authentification

1) Standard Flow Enabled
	*Flux d'authentification basé sur OpenID Connect et OAuth 2.0
	"Authorization Code" <-échange-> "Access Token" *
2) Implicit Flow Enabled
	*“Access Token” <-échange-> "Authentification utilisateur"*
3) Direct Access Grants Enabled
	*"Access Token" <- échange -> "nom, mot de passe"*

___
# Gestion des Identités

1) User Federation Providers
	*Se connecter avec les services externes (LDAP, Active Directory)*
2) Identity Provider Federations
	*S'authentifier avec Google, Facebook etc*

___
# Conclusion

	Keycloak est une solution de sécurité incontournable qui allie rigueur, adaptabilité 
	et simplicité grâce à ses puissantes fonctionnalités d’authentification et
	d’autorisation.