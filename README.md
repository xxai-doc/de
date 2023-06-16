<p align="center"><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/logo.svg"/></a><br/><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/xxai.svg"/></a></p><p align="center"><a href="https://github.com/xxai-art/doc#readme"><img alt="I18N" src="https://cdn.jsdelivr.net/gh/wactax/img/t.svg"/></a>　<a href="https://groups.google.com/u/0/g/xxai-art"><img alt="Google Groups" src="https://cdn.jsdelivr.net/gh/wactax/img/g-groups.svg"/></a></p>

# xxAI.art

Ein Teil des Website-Codes ist Open Source und kann gerne zur Optimierung der Übersetzung beitragen.

## Front-End-Code

* [Front-End-Code](https://github.com/xxai-art/web)
* [Sprachpakete für die Website als Ganzes](https://github.com/xxai-art/web/tree/main/i18n)
* [Sprachpakete für Anmeldemodule](https://github.com/wacpkg/user/tree/main/ui.i18n)
* [Mehrsprachige Website-Dokumentation](https://github.com/xxai-doc)

Die Front-End-Programmiersprache ist [@w5/coffee_plus](http://npmjs.com/@w5/coffee_plus) , die einige Funktionen basierend auf der Coffeescript-Syntax hinzufügt, siehe [./coffee_plus.md](./coffee_plus.md) .

## Internationalisierung von Websites und Dokumenten

Bauen Sie auf den folgenden 3 Projekten auf

### [@w5/mdt](https://www.npmjs.com/package/@w5/mdt)

Die Markdown-Vorlage mit dem Suffix `.mdt` kann auf externe Dateien mit einer Syntax ähnlich wie `<+ ./coffee_plus/import.js>` verweisen.

[@w5/trmd](https://www.npmjs.com/package/@w5/trmd)

Die Markdown-Übersetzung übersetzt keine Codes und Links und speichert übersetzte Sätze zwischen. Wenn die Übersetzung geändert wird, der Originaltext jedoch nicht, wird die Änderung der Übersetzung durch eine erneute Ausführung nicht überschrieben.

[@w5/i18n](https://www.npmjs.com/package/@w5/i18n)

Sprachdateien zum Übersetzen `yaml` generierten Websites.
