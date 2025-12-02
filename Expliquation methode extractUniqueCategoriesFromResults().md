
async function extractUniqueCategoriesFromResults(page: Page) {  
  const locators = await page  
    .locator('table tbody tr td:nth-child(3) .div-plate')  
    .all();  
  const texts = await Promise.all(locators.map(async (el) => await el.textContent())  
    .filter((text) => text !== null) as Promise<string>[]);  
  const uniqueCategories = new Set(texts);  
  return Promise.resolve(uniqueCategories);  
}


c'est une fonction asynchrone,
page est en parametres (ce qui veut dire que la methode a besoin de lire la page)
on pointe sur le locator "un elements div-plate dans la troisieme colone du tableau" identifiée comme "catégories"
on prends en comptes tout .all
on crée une table de strings textes qui va correspondre aux elements qu'on recupere dans le tableau
elle utilise des promesses; 
