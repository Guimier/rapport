Modèle de rapport dans le format ISIMA en LaTeX.

Utilisation
----

Un script `init` est fourni pour commencer un rapport. Une fois celui-ci exécuté, le dossier `contenu` contiendra les fichiers indispensable au fonctionnement de ce modèle.

Je conseille de ne pas utiliser directement la racine pour les fichiers modifiés ou ajoutés, mais je m’efforcerai d’éviter les modification incompatibles avec une fusion -- à part ce que je ne peux pas mettre autre part sans réduire l’utilisabilité. Je me réserve tous les noms commençant pas `._` à la racine comme espace pour organiser mon architecture.

**Note :** je vais essayer de déplacer les bibliographies, ce qui pourrait être un changement incompatible.

Une fois la configuration initiale effectuée (voir `configuration.tex`), le rapport peut être construit avec le script `build`. Un script `clean` permet d'obtenir un effet semblable au comportement par défaut de Texlipse (en configurant un *builder* dans Eclipse pour exécuter `bash -c "mv tmp/* . 2>/dev/null; ./build; ./clean --tmp"`).

`configuration.tex`
----
Pour fonctionner, ce modèle nécessite un minimum de configuration, à placer dans le fichier `contenu/configuration.tex`. Une liste des instructions de configuration est disponible dans le fichier `contenu/configuration.modele.tex`.

Ce fichier est inclus en préambule, il peut donc servir à appeler des paquets supplémentaires ou à définir des macros.
