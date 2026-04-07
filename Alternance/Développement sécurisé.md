Checklist de sécurité dans le développement (Secure by Design)

méthode de "threat modeling" (STRIDE,EBIOS,ATT&CK) -> anticipation;

attribution des droits; séparation des privilèges;

traçabilités des actions;

RGPD -> utilisation des informations (données personnelles)

authentification multifactorielle;

stockage de mdp sécurisés -> Argon2; bcrypt (hachage fort et salé)

gestion des identités -> LDAP; Active Directory

protection des données sensibles ->  chiffrement AES 256

HTTPS et TLS -> les communications doivent être protégées en externe et en interne

chiffrement des données au repos -> Bitlocker, LUKS;

sécurité du code -> outils d'analyse statique : SonarQube, Checkmarx, intégrer à la pipeline CI/CD;

revues de code régulières -> pair programing, pull request, checklist OWASP;

suivre les dépendances externes (Snyk);

bonnes pratiques de codage : sanitation;

test de sécurité : 

pentest;

tester les vulnérabilités : injections; DoS; test automatisés sur les pipeline CI/CD;

protéger les API avec l'authentification -> OAuth, clé API;

contrôle d'accès stricte de l'environnement de production;



LIRE LE DOCUMENT : TIRER LES CONCLUSION