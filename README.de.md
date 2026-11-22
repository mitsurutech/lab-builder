# lab-builder: Images für Container-Labs aus dem öffentlichen GitHub-Repository einer Lehrkraft bauen

[English](README.md) | [Français](README.fr.md) | [Español](README.es.md) | [日本語](README.ja.md) | [Deutsch](README.de.md)

Baut die Dienste eines [MitsuruTech-Container-Labs](https://mitsurutech.co.uk/de/help/labs) aus dem
öffentlichen GitHub-Repository einer Lehrkraft und veröffentlicht jedes Image unter
[`ghcr.io/mitsurutech/lab-images`](https://github.com/orgs/mitsurutech/packages/container/package/lab-images).

Ein Lab ist eine Gruppe von Containern, die eine Compose-Datei beschreibt. Wenn eine Lehrkraft einen
Commit eines Labs veröffentlicht, dessen Compose-Datei `build:` enthält, startet die Website hier
`Build a lab image`, einmal pro gebautem Dienst. Das Image erhält das Tag `<lab>-<service>-<commit>`,
und die Lab-Maschinen ziehen es von dort. Das Dockerfile einer Lehrkraft läuft nie auf einer Lab-Maschine.

**Was veröffentlicht wird, ist öffentlich.** Nur öffentliche Repositorys werden gebaut. Alles, was ein
Dockerfile hineinkopiert, und jeder Wert, den es mit `ENV` oder `ARG` setzt, kann von jedem gelesen
werden, der das Image zieht: Bewahren Sie Geheimnisse in einer `env_file` auf, die die Website beim
Start einer Kopie hinzufügt und die nie in das Image gebaut wird.

Die Builds laufen auf GitHubs eigenen Runnern und werden nur von der Website gestartet, mit einem Token,
das sonst nichts kann. Um ein Image zu melden, das nicht hierher gehört, schreiben Sie an die Adresse
auf mitsurutech.co.uk/de/contact.

## Lizenz

Dieses Werk steht unter der Lizenz [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/). Sie dürfen es zum Lernen und Unterrichten teilen und bearbeiten, sofern Sie Mitsuru Technologies Ltd nennen, es nicht kommerziell nutzen und alles, was Sie daraus machen, unter derselben Lizenz teilen. Der vollständige Text steht in der Datei `LICENSE`.

## Über dieses Projekt

Erstellt von [Mitsuru Technologies](https://mitsurutech.co.uk/de) für die
[MitsuruTech Learning Platform](https://mitsurutech.co.uk/de/learning): Python, Java, Go, Node, SQL und
Linux im Browser für Schulen und Colleges, mit Container-Labs, aus GitHub bereitgestellten Web-Apps und
Quizzen, die sich selbst bewerten. Probieren Sie Code ohne Konto im
[Playground](https://mitsurutech.co.uk/de/playground) aus.

Sie unterrichten eine Klasse? Sehen Sie sich [den Preis](https://mitsurutech.co.uk/de/pricing) an oder [legen Sie ein Schulkonto an](https://mitsurutech.co.uk/de/signup).
