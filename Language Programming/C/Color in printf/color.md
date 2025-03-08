En C, vous pouvez utiliser des séquences d'échappement ANSI pour changer les couleurs du texte et du fond lorsque vous utilisez `printf`. Ces séquences d'échappement permettent de modifier l'apparence du texte dans les terminaux qui supportent les codes ANSI.

### Couleurs de Texte

Voici un tableau des couleurs que vous pouvez utiliser pour le texte et le fond :

| Couleur | Texte      | Fond       |
| ------- | ---------- | ---------- |
| Noir    | `\033[30m` | `\033[40m` |
| Rouge   | `\033[31m` | `\033[41m` |
| Vert    | `\033[32m` | `\033[42m` |
| Jaune   | `\033[33m` | `\033[43m` |
| Bleu    | `\033[34m` | `\033[44m` |
| Magenta | `\033[35m` | `\033[45m` |
| Cyan    | `\033[36m` | `\033[46m` |
| Blanc   | `\033[37m` | `\033[47m` |
| Reset   | `\033[0m`  | N/A        |

### Exemple d'utilisation

Pour utiliser ces codes, vous incluez les séquences d'échappement dans votre chaîne de formatage. N'oubliez pas de réinitialiser la couleur après votre texte pour éviter que les changements de couleur n'affectent le texte suivant.

Voici un exemple simple :

```c
#include <stdio.h>

int main() {
    printf("\033[31mCe texte est rouge.\033[0m\n");
    printf("\033[32mCe texte est vert.\033[0m\n");
    printf("\033[33mCe texte est jaune.\033[0m\n");
    printf("\033[34mCe texte est bleu.\033[0m\n");
    printf("\033[35mCe texte est magenta.\033[0m\n");
    printf("\033[36mCe texte est cyan.\033[0m\n");
    printf("\033[37mCe texte est blanc.\033[0m\n");
    printf("\033[1;31mCe texte est rouge et en gras.\033[0m\n");
    printf("\033[1;32mCe texte est vert et en gras.\033[0m\n");
    printf("\033[44m\033[37mTexte blanc sur fond bleu.\033[0m\n");

    return 0;
}
```

### Explication des Codes

- `\033[`: Commence la séquence d'échappement.
- `0m`: Réinitialise tous les attributs (texte normal, couleur par défaut).
- `30m` à `37m`: Définit la couleur du texte (de 30 à 37).
- `40m` à `47m`: Définit la couleur du fond (de 40 à 47).
- `1;`: Ajoute un attribut de style (par exemple, `1;` pour le gras).

### Combinaison de Codes

Vous pouvez combiner différents codes pour obtenir des effets multiples comme le texte en gras ou avec un fond coloré. Par exemple :

```c
printf("\033[1;31;47mTexte rouge en gras sur fond blanc.\033[0m\n");
```

### Conclusion

En utilisant ces séquences d'échappement ANSI dans `printf`, vous pouvez colorer et styliser le texte dans le terminal. Cela peut être particulièrement utile pour améliorer la lisibilité ou l'esthétique de la sortie de votre programme.