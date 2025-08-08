
ImageTag (et sa version) se trouve dans les annotations dans le cas ou il n'y a pas de argocd image updater -> dans valuesObject

sinon, s'il y a image updater -> recuperer juste l'image

parenthèse pas fermée :

- String cluster = spec.getDestination().getName() -> retourne null car les noms ne sont pas notés dans la spec

- résolu : création des champs dans application.properties 