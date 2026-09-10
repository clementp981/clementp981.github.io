# Compte-rendu - FOAF (Friend Of A Friend) - PILOTTE Clément

## Exercice 1

### Objectif

Se décrire pour le Web sémantique en publiant un fichier RDF (`foaf.rdf`),
relié a une page de presentation (`index.html`), le tout hebergé sur GitHub Pages.

### Ce qui a été fait

1. Rédaction du fichier `foaf.rdf` au format RDF/XML avec plusieurs éléments de
   vocabulaire FOAF vu durant le CM.
   (name, givenName, familyName, homepage, interest, knows, based_near...).
2. Création de la page `index.html` qui référence le fichier FOAF dans son en-tete :

   ```html
   <link rel="meta" type="application/rdf+xml" title="FOAF" href="https://github.com/clementp981/clementp981.github.io/blob/main/foaf.rdf">
   ```

3. Dépôt des deux fichiers sur un dépôt GitHub nomme `https://clementp981.github.io/`,
   ce qui active automatiquement GitHub Pages.
4. Mise en ligne : la page est accessible sur `https://clementp981.github.io/`
   et le fichier FOAF sur `https://github.com/clementp981/clementp981.github.io/blob/main/foaf.rdf`.
5. Validation du fichier avec le validateur RDF du W3C
   (`https://www.w3.org/RDF/Validator/`), qui extrait correctement les triplets.

   ![img.png](img.png)

### Points relevés/appris

- **mbox_sha1sum** : l'adresse mail n'est pas écrite en clair mais sous forme
  d'empreinte sha1 de l'URI `mailto:...`. Cela évite le ramassage automatique
  de l'adresse par des robots.
- **knows et rdfs:seeAlso** : la propriete `knows` relie deux personnes, et
  `rdfs:seeAlso` indique ou trouver le fichier FOAF de l'autre personne. C'est
  ce qui permet a un crawler de suivre les liens d'un profil a l'autre.

