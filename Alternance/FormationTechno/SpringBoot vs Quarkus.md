
*Raison pour laquelle GCA est passé de Spring à Quakus*

	L'arrivé de cloud -> Spring n'est plus adapté; par exemple le temps de démarrage est 
	long (peut prendre plusieurs minutes)

- Spring 3 - amélioré et atteint des meilleurs performances

**Quarkus dès sa création est adapté au cloud donc il a des meilleures performances.**

| **Critère**                | **Spring Boot**                                                 | **Quarkus**                                                    |
| -------------------------- | --------------------------------------------------------------- | -------------------------------------------------------------- |
| **Créé par**               | Pivotal (VMware)                                                | Red Hat                                                        |
| **Philosophie**            | Facilité de développement avec beaucoup d’automatisations       | Optimisé pour le cloud et les environnements natifs Kubernetes |
| **Performance**            | Bonne, mais plus lente au démarrage et consomme plus de mémoire | Démarrage ultra-rapide, faible empreinte mémoire               |
| **Utilisation principale** | Applications Java classiques, API REST, microservices           | Microservices cloud-native, conteneurs, Serverless             |
| **Framework sous-jacent**  | Basé sur Spring                                                 | Basé sur Vert.x et CDI (Jakarta EE)                            |
| **Compatibilité**          | Très répandu, énorme écosystème                                 | Compatible GraalVM, optimisé pour Kubernetes                   |
| **Outils natifs**          | Spring Data, Spring Security, Spring Cloud                      | Hibernate ORM avec Panache, Quarkus Dev Mode                   |
