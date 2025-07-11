- **SSR (Server-Side Rendering)** : Génère le HTML côté serveur avant d’envoyer la page au client, améliorant ainsi le **SEO** et le **temps de chargement initial**.
- **Hydratation** : Une fois la page chargée, Angular associe les événements et réactive l’application côté client pour une navigation fluide, sans recharger toute la page.

## **Mise en place de SSR & Hydratation**

| ng add @angular/universal  # Ajoute SSR à votre projet Angular              |
| --------------------------------------------------------------------------- |
| npm run dev:ssr            # Lance l'application avec le rendu côté serveur |
 