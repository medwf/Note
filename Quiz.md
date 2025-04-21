---    TYPE SCRIPTE 1



### **QCM 1 : Qu'est-ce que TypeScript ?**
**A.** Un langage compilé vers du Java  
**B.** Une surcouche typée de JavaScript  
**C.** Une base de données orientée document  
**D.** Un langage uniquement utilisé pour le backend 



























**✅ Réponse correcte :** B  
**💡 Explication :** TypeScript est un sur-ensemble de JavaScript qui ajoute un système de types.

---

### **QCM 2 : Quel outil est utilisé pour compiler le code TypeScript ?**
**A.** Node.js  
**B.** npm  
**C.** tsc  
**D.** ts-node 































**✅ Réponse correcte :** C  
**💡 Explication :** Le compilateur TypeScript est appelé `tsc` (TypeScript Compiler).

---

### **QCM 3 : Quelle extension de fichier est utilisée pour les fichiers TypeScript ?**
**A.** .js  
**B.** .jsx  
**C.** .ts  
**D.** .tsx uniquement  
**✅ Réponse correcte :** C  
**💡 Explication :** Les fichiers TypeScript portent l’extension `.ts`, et `.tsx` pour les fichiers avec JSX.

---

### **QCM 4 : Quel est l’avantage principal de TypeScript par rapport à JavaScript ?**
**A.** Il est plus rapide à exécuter  
**B.** Il permet l’accès aux bases de données  
**C.** Il ajoute des types statiques  
**D.** Il fonctionne uniquement avec Angular  
**✅ Réponse correcte :** C  
**💡 Explication :** Le typage statique permet de détecter des erreurs à la compilation.

---

### **QCM 5 : Quelle commande permet d'initialiser un projet TypeScript ?**
**A.** `npm init typescript`  
**B.** `tsc init`  
**C.** `tsc --init`  
**D.** `init-ts`  
**✅ Réponse correcte :** C  
**💡 Explication :** La commande `tsc --init` crée un fichier `tsconfig.json` pour configurer un projet TypeScript.

---

Parfait ! Voici une nouvelle série de **QCM** supplémentaires basés sur le contenu du document *TypeScript1.pdf* :

---

### **QCM 6 : Quelle est la commande pour compiler un fichier TypeScript nommé `index.ts` ?**
**A.** `node index.ts`  
**B.** `npm index.ts`  
**C.** `tsc index.ts`  
**D.** `compile index.ts`  
**✅ Réponse correcte :** C  
**💡 Explication :** La commande `tsc index.ts` utilise le compilateur TypeScript pour générer un fichier JavaScript.

---

### **QCM 7 : Quelle déclaration permet de définir une variable de type chaîne en TypeScript ?**
**A.** `let nom: string = "Jean";`  
**B.** `let nom = "Jean": string;`  
**C.** `string nom = "Jean";`  
**D.** `var string nom = "Jean";`  
**✅ Réponse correcte :** A  
**💡 Explication :** En TypeScript, le typage se fait avec la syntaxe `nom: type`.

---

### **QCM 8 : Quelle est la bonne syntaxe pour déclarer un tableau de nombres ?**
**A.** `let nombres: number[] = [1, 2, 3];`  
**B.** `let nombres: [number] = [1, 2, 3];`  
**C.** `let nombres = [1, 2, 3]: number[];`  
**D.** `let nombres: array<number> = [1, 2, 3];`  
**✅ Réponse correcte :** A  
**💡 Explication :** Le type tableau s’écrit `type[]`, donc ici `number[]`.

---

### **QCM 9 : Quel type spécial permet de représenter une valeur qui peut être de plusieurs types ?**
**A.** `mixed`  
**B.** `union`  
**C.** `multi`  
**D.** `|`  
**✅ Réponse correcte :** D  
**💡 Explication :** On utilise l’opérateur `|` pour les types unions, ex : `string | number`.

---

### **QCM 10 : Que signifie le mot-clé `readonly` dans TypeScript ?**
**A.** Il indique que la propriété est privée  
**B.** Il interdit de modifier la valeur après affectation  
**C.** Il transforme un champ en champ statique  
**D.** Il rend la variable visible uniquement en lecture pour l’extérieur  
**✅ Réponse correcte :** B  
**💡 Explication :** `readonly` empêche toute réaffectation après la première valeur définie.

---

Parfait ! Voici une **troisième série de QCM** basée sur la suite du document *TypeScript1.pdf* :

---

### **QCM 11 : Quel mot-clé permet de définir une interface en TypeScript ?**
**A.** `interface`  
**B.** `type`  
**C.** `structure`  
**D.** `object`  
**✅ Réponse correcte :** A  
**💡 Explication :** Le mot-clé `interface` permet de définir des structures d’objets typées.

---

### **QCM 12 : Quelle est la principale différence entre `interface` et `type` en TypeScript ?**
**A.** `interface` est utilisé pour les fonctions uniquement  
**B.** `type` ne permet pas l'héritage  
**C.** `type` peut représenter des unions, contrairement à `interface`  
**D.** `interface` est plus rapide que `type` à l'exécution  
**✅ Réponse correcte :** C  
**💡 Explication :** Les `type` peuvent définir des unions de types, ce que les `interface` ne peuvent pas faire directement.

---

### **QCM 13 : Quel mot-clé permet d’implémenter une interface dans une classe ?**
**A.** `extends`  
**B.** `use`  
**C.** `with`  
**D.** `implements`  
**✅ Réponse correcte :** D  
**💡 Explication :** On utilise `implements` pour indiquer qu’une classe respecte une interface.

---

### **QCM 14 : Que se passe-t-il si une classe ne respecte pas toutes les propriétés d'une interface ?**
**A.** Le code s’exécute normalement  
**B.** Une erreur est générée à l'exécution  
**C.** Une erreur est détectée à la compilation  
**D.** La classe est automatiquement complétée  
**✅ Réponse correcte :** C  
**💡 Explication :** TypeScript vérifie la conformité aux interfaces à la compilation.

---

### **QCM 15 : Quelle syntaxe permet de rendre une propriété optionnelle dans une interface ?**
**A.** `nom?: string`  
**B.** `nom: string | undefined`  
**C.** `optional nom: string`  
**D.** `string nom?`  
**✅ Réponse correcte :** A  
**💡 Explication :** L’ajout d’un `?` après le nom rend la propriété optionnelle.

---

Parfait ! On va compléter avec des **QCM supplémentaires** pour **couvrir tout le document `TypeScript1.pdf`** de manière pédagogique et complète.

---

### **QCM 16 : Comment définit-on une fonction typée en TypeScript ?**
**A.** `function maFonction(x, y): number { return x + y; }`  
**B.** `function maFonction(x: number, y: number): number { return x + y; }`  
**C.** `maFonction = (x, y) => x + y`  
**D.** `function maFonction(x: number, y: number) => number`  
**✅ Réponse correcte :** B  
**💡 Explication :** TypeScript permet d’annoter les types des paramètres et du retour.

---

### **QCM 17 : Quel type spécial permet de ne rien retourner dans une fonction ?**
**A.** `null`  
**B.** `undefined`  
**C.** `never`  
**D.** `void`  
**✅ Réponse correcte :** D  
**💡 Explication :** Le type `void` indique qu'une fonction ne retourne rien.

---

### **QCM 18 : Lequel de ces types empêche toute valeur d'être retournée ou atteinte ?**
**A.** `any`  
**B.** `void`  
**C.** `never`  
**D.** `unknown`  
**✅ Réponse correcte :** C  
**💡 Explication :** `never` est utilisé pour des fonctions qui ne retournent jamais (ex : une exception).

---

### **QCM 19 : Quel mot-clé permet de définir un type générique dans une fonction ?**
**A.** `function<T>()`  
**B.** `func<T>()`  
**C.** `def<T>()`  
**D.** `type<T>()`  
**✅ Réponse correcte :** A  
**💡 Explication :** Le mot-clé `function` peut être suivi de `<T>` pour créer une fonction générique.

---

### **QCM 20 : Quel est le rôle d’un type générique (`<T>`) ?**
**A.** Créer des fonctions plus rapides  
**B.** Masquer les types réels au compilateur  
**C.** Permettre la réutilisabilité de la fonction avec différents types  
**D.** Empêcher l'utilisation de types personnalisés  
**✅ Réponse correcte :** C  
**💡 Explication :** Les génériques permettent d’écrire des fonctions qui s’adaptent au type utilisé.

---

### **QCM 21 : Quelle syntaxe permet de faire une *type assertion* en TypeScript ?**
**A.** `val as string`  
**B.** `assert(val, string)`  
**C.** `typeof val == string`  
**D.** `cast val as string`  
**✅ Réponse correcte :** A  
**💡 Explication :** Une assertion de type se fait avec `as`, comme dans `val as string`.

---

### **QCM 22 : Lequel de ces types est utilisé pour éviter les erreurs lors de la migration depuis JavaScript ?**
**A.** `void`  
**B.** `never`  
**C.** `any`  
**D.** `unknown`  
**✅ Réponse correcte :** C  
**💡 Explication :** Le type `any` désactive le typage, pratique mais risqué.

---

### **QCM 23 : Quelle est la différence entre `any` et `unknown` ?**
**A.** Aucune différence  
**B.** `unknown` impose une vérification avant d'être utilisé  
**C.** `any` est plus sûr que `unknown`  
**D.** `unknown` permet plus d'erreurs que `any`  
**✅ Réponse correcte :** B  
**💡 Explication :** `unknown` est plus sûr car on doit vérifier son type avant utilisation.

---

### **QCM 24 : À quoi sert le mot-clé `enum` en TypeScript ?**
**A.** Créer des fonctions  
**B.** Déclarer des types d’erreurs  
**C.** Définir des ensembles de constantes nommées  
**D.** Définir des objets génériques  
**✅ Réponse correcte :** C  
**💡 Explication :** `enum` permet de déclarer un ensemble de constantes accessibles par un nom.

---

### **QCM 25 : Comment exporter une fonction ou une variable dans un module TypeScript ?**
**A.** `expose`  
**B.** `public`  
**C.** `export`  
**D.** `send`  
**✅ Réponse correcte :** C  
**💡 Explication :** Le mot-clé `export` permet de rendre une entité accessible dans d’autres fichiers.

---
