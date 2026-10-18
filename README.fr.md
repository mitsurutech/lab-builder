# lab-builder : construire des images de lab de conteneurs depuis le dépôt GitHub public d’un enseignant

[English](README.md) | [Français](README.fr.md) | [日本語](README.ja.md) | [Español](README.es.md)

Construit les services d’un [lab de conteneurs MitsuruTech](https://mitsurutech.co.uk/fr/help/labs) à partir du dépôt
GitHub public d’un enseignant, et publie chaque image sur
[`ghcr.io/mitsurutech/lab-images`](https://github.com/orgs/mitsurutech/packages/container/package/lab-images).

Un lab est un ensemble de conteneurs décrit par un fichier compose. Lorsqu’un enseignant publie un commit
d’un lab dont le fichier compose contient `build:`, le site lance ici `Build a lab image` une fois
par service à construire. L’image porte l’étiquette `<lab>-<service>-<commit>`, et les machines de lab la récupèrent
à cet endroit. Aucun Dockerfile d’enseignant ne s’exécute jamais sur une machine de lab.

**Ce qui est publié est public.** Seuls les dépôts publics sont construits. Tout ce qu’un Dockerfile
copie, et toute valeur qu’il définit avec `ENV` ou `ARG`, peut être lu par quiconque récupère
l’image : gardez les secrets dans un `env_file`, que le site ajoute au démarrage d’une copie et qui
n’est jamais intégré à l’image.

Les constructions s’exécutent sur les runners de GitHub, lancées uniquement par le site avec un jeton qui ne peut
rien faire d’autre. Pour signaler une image qui ne devrait pas être ici, écrivez à l’adresse indiquée sur la
[page de contact](https://mitsurutech.co.uk/fr/contact) de mitsurutech.co.uk.

## Licence

Cette œuvre est sous licence [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/). Vous pouvez la partager et l’adapter pour apprendre et enseigner, à condition de citer Mitsuru Technologies Ltd, de ne pas l’utiliser commercialement et de partager tout ce que vous en tirez sous la même licence. Le texte complet est dans le fichier `LICENSE`.

## À propos

Réalisé par [Mitsuru Technologies](https://mitsurutech.co.uk/fr) pour la
[plateforme d’apprentissage MitsuruTech](https://mitsurutech.co.uk/fr/learning) : Python, Java, Go, Node, SQL et
Linux dans le navigateur pour les écoles et les établissements, avec des labs de conteneurs, des applications web déployées depuis GitHub et
des quiz corrigés automatiquement. Essayez du code sans compte dans le
[bac à sable](https://mitsurutech.co.uk/fr/playground).

Vous enseignez à une classe ? Consultez [le prix](https://mitsurutech.co.uk/fr/pricing) ou [créez un compte d’établissement](https://mitsurutech.co.uk/fr/signup).
