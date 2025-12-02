17.10.2025

- wiki sur l'integration de playwright dans un projet (archtecture : infos général, mise place, cas concret)
- integration playwright dans le pblave (à préciser)
- sujet de bind entre intellij et sonarqube

- se renseigner sur le RAG et voir comment rendre le wiki utilisable par l'IA

### Partie 1 : Infos Generales

Paywright est un outil de test end to end (e2e)
Objectif : simuler les actions d'utilisateur dans un navigateur.

Composants clé : Playwright Test Runner; Playwright Inspector; Codegen; Trace Viewer;

### Partie 2 : Mise en Place

npm playwright install --with-deps

structure de projet typique

project/
├── tests/
│   ├── example.spec.ts
├── playwright.config.ts
├── package.json
└── test-results/

Configuration du projet playwright.config.ts


import { defineConfig } from '@playwright/test';

export default defineConfig({
  testDir: './tests',
  retries: 1,
  use: {
    headless: true,
    screenshot: 'on',
    trace: 'on-first-retry',
  },
  projects: [
    { name: 'chromium' },
    { name: 'firefox' },
    { name: 'webkit' },
  ],
});



lancer le test playwright test

pour les autres outils :

npx playwright codegen localhost:4200

npx playwright show-report

npx playwright show-trace test-results/trace.zip


Exemple de test :

import { test, expect } from '@playwright/test';

test('Vérifie la récupération des clusters ArgoCD', async ({ page }) => {
  await page.goto('http://localhost:4200');
  await page.getByText('Activer la sélection').click();
  const clusters = await page.locator('.cluster-card');
  await expect(clusters).toHaveCountGreaterThan(0);
});

### Partie 3 : Projet  concret dashboardKube-Front

On va faire les test playwright dans le frontend de l'application. 

