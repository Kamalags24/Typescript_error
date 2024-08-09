# Typescript_error

Lors de l'utilisation de TypeScript, plusieurs types d'erreurs peuvent survenir, allant des erreurs de compilation aux erreurs d'exécution. Voici quelques-unes des erreurs les plus courantes :

### 1. **Erreurs de compilation**
   - **Erreurs de typage** : TypeScript est strict sur les types, donc si vous essayez d'attribuer une valeur d'un type incompatible à une variable, vous obtiendrez une erreur.
     - **Exemple** : 
       ```typescript
       let age: number = "trente"; // Error: Type 'string' is not assignable to type 'number'
       ```

   - **Propriétés manquantes ou supplémentaires** : Si un objet ne respecte pas strictement l'interface ou le type attendu, TypeScript génère une erreur.
     - **Exemple** :
       ```typescript
       interface User {
           name: string;
           age: number;
       }
       
       let user: User = { name: "John" }; // Error: Property 'age' is missing
       ```

   - **Erreurs liées aux modules** : Mauvaise configuration des chemins des modules, imports ou exports incorrects.
     - **Exemple** :
       ```typescript
       import { nonExistentModule } from './module'; // Error: Cannot find module './module'
       ```

   - **Erreurs de compatibilité entre versions de TypeScript** : Certaines fonctionnalités peuvent ne pas être disponibles dans des versions plus anciennes de TypeScript.

### 2. **Erreurs d'exécution (Runtime)**
   - **Erreurs de type non capturées** : Si vous utilisez le `any` ou si vous ignorez les avertissements de TypeScript, des erreurs de type peuvent survenir à l'exécution.
     - **Exemple** :
       ```typescript
       let data: any = "hello";
       console.log(data.toFixed(2)); // Runtime Error: data.toFixed is not a function
       ```

   - **Accès à des propriétés ou méthodes non définies** : Même si TypeScript vérifie les types à la compilation, il ne peut pas garantir que des objets dynamiques auront toujours les propriétés attendues.
     - **Exemple** :
       ```typescript
       let obj: { [key: string]: any } = {};
       console.log(obj.nonExistentProperty()); // Runtime Error: obj.nonExistentProperty is not a function
       ```

### 3. **Erreurs de configuration**
   - **Mauvaise configuration de `tsconfig.json`** : Une mauvaise configuration du fichier `tsconfig.json` peut entraîner des erreurs lors de la compilation ou même empêcher TypeScript de fonctionner correctement.
     - **Exemple** : Oublier d'inclure des répertoires ou des fichiers importants dans `include`.

   - **Conflit entre `tsconfig.json` et les linters** : Des conflits peuvent survenir si les règles définies dans `tsconfig.json` diffèrent de celles configurées dans un linter comme ESLint.

### 4. **Erreurs liées aux bibliothèques externes**
   - **Absence de types** : Lors de l'utilisation de bibliothèques JavaScript avec TypeScript, si des définitions de types (`@types/...`) ne sont pas disponibles, cela peut entraîner des erreurs ou des avertissements.
     - **Exemple** : 
       ```typescript
       import * as someLib from 'some-lib'; // Error: Could not find a declaration file for module 'some-lib'
       ```

   - **Types mal définis** : Parfois, les définitions de types fournies par des bibliothèques tierces sont incorrectes ou incomplètes.

### 5. **Erreurs liées à l'inférence de types**
   - **Inférence incorrecte de types** : TypeScript essaie d'inférer les types automatiquement, mais dans certains cas, cela peut entraîner des erreurs si l'inférence n'est pas correcte.
     - **Exemple** :
       ```typescript
       let data = fetchData(); // TypeScript infers 'any', leading to potential runtime issues
       ```

En utilisant les outils de développement TypeScript et en suivant les bonnes pratiques, beaucoup de ces erreurs peuvent être anticipées et évitées.


