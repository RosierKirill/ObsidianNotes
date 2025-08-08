
Les tests doivent pas être dependants des environnement, et reproductible (local/ CI CD)

le code doit etre validé par sonar

quarkus demarre des conteneurs automatiquement : keycloak, kube etc

types de tests : 

- tests unitaires (mocks, pas Quarkus)
- test d'integration (mock)
- test 

mocks : mockito, pour les methodes avec un algorithme complexe ( il est tres libre, car ont peut coder ce qu'on veut, il faut faire attention caar il faut que le code corresponde a la vrai methode)

dans given() on peut mettre le token d'authorization pour authentificaiton

graalvm est utilisé comme machine virtuelle au lieu de build en binaire -> un build livrable (.exe) natif (windows, linux) 

test natif sert a tester si les tests en jvm fonctionnent avec la machine virtuelle (native) aussi

