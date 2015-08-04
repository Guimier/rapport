Modèle de rapport dans le format ISIMA en LaTeX.

Utilisation
----

Un script `init` est fourni pour commencer un rapport. Une fois celui-ci
exécuté, le dossier `contenu` contiendra les fichiers indispensable au
fonctionnement de ce modèle.

Je conseille de ne pas utiliser directement la racine pour les fichiers modifiés
ou ajoutés, mais je m’efforcerai d’éviter les modification incompatibles avec
une fusion -- à part ce que je ne peux pas mettre autre part sans réduire
l’utilisabilité. Je me réserve tous les noms commençant pas `._` à la racine
comme espace pour organiser mon architecture.

Une fois la configuration initiale effectuée (voir `configuration.tex`),
le rapport peut être construit avec le script `build`. Un script `clean`
permet de supprimer les fichiers créés par la compilation.

**Note en cas d'erreur de compilation :** le script de compilation ne fonctionne actuellement pas si ni la bibliographie ni la webographie ne sont *utilis�es* (appel�es dans le texte avec \cite et \webcite).

`configuration.tex`
----
Pour fonctionner, ce modèle nécessite un minimum de configuration, à placer dans
le fichier `configuration.tex`. Une liste des instructions de
configuration est disponible dans le fichier `configuration.modele.tex`.

Ce fichier est inclus en préambule, il peut donc servir à appeler des paquets
supplémentaires ou à définir des macros.

`clean`
----
Ce script a trois options pour modifier son comportement : `--tmp` déplace les
fichiers dans le dossier `tmp` (ils sont supprimés par défaut), `--all`
supprime aussi le résultat de la compilation, `--quiet` supprime la sortie
standard (les commandes exécutées sont affichées sinon).

Drapeaux
----
Un système de drapeaux est inclus, qui permet de modifier le comportement de la
compilation sans modifier le fichier de configuration. Il est constitué :
    - de deux scripts `flag` et `unflag` permettant d'activer ou de
      désactiver des comportements ;
    - d'un script `flags` indiquant l'état actuel des drapeaux ;
    - d'une macro `\ifflag` permettant de tester l'état d'un drapeau.

Le système est conçu pour être étendu : vous pouvez créer un fichier
`flags.csv` définissant des drapeaux supplémentaires. Celui-ci doit contenir
des ligne de la forme :

    nom,l,id,Explication succinte

Le premier champ est le nom utilisé pour la commande `flag`, le second est un
nom alternatif pour cette même commande (je l'utilise pour raccourcir à un
caractère). Le troisième champ est l'identifiant utilisé dans `\ifflag` et le
dernier est une explication affichée dans l'aide de `flag` (lors d'un appel
sans arguments).

L'implémentation actuelle crée un fichier `id.mrp` (`id` étant l'identifiant
mentionné précédemment), format qui peut facilement être ajouté dans le fichier
`.gitignore`. Cette implémentation pourrait changer, mais la facilité
d'exlusion restera.
