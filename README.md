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

* [@w5/mdt](https://www.npmjs.com/package/@w5/mdt)

  Das Suffix ist `.mdt` . Sie können die Syntax ähnlich wie `<+ ./coffee_plus/import.js>` verwenden, um auf externe Dateien zu verweisen und Markdown mit dem Suffix `.md` zu generieren.

* [@w5/trmd](https://www.npmjs.com/package/@w5/trmd)

  Die Markdown-Übersetzung übersetzt keine Codes und Links und speichert übersetzte Sätze zwischen. Wenn die Übersetzung geändert wird, der Originaltext jedoch nicht, wird die Änderung der Übersetzung durch eine erneute Ausführung nicht überschrieben.

* [@w5/i18n](https://www.npmjs.com/package/@w5/i18n)

  Sprachdateien zum Übersetzen `yaml` generierten Websites.

### Anweisungen zur Automatisierung der Dokumentübersetzung

Siehe Repository [xxai-art/doc](https://github.com/xxai-art/doc)

Es wird empfohlen, zuerst NodeJS, [Direnv](https://direnv.net) und [Bun](https://github.com/oven-sh/bun) zu installieren und dann nach Eingabe des Verzeichnisses `direnv allow` auszuführen.

Um zu vermeiden, dass zu große Warehouses in Hunderte von Sprachen übersetzt werden, habe ich für jede Sprache ein separates Code-Warehouse erstellt und eine Organisation zum Speichern dieses Warehouse erstellt

Durch Festlegen der Umgebungsvariablen `GITHUB_ACCESS_TOKEN` und anschließendes Ausführen von [create.github.coffee](https://github.com/xxai-art/doc/blob/main/create.github.coffee) wird das Warehouse automatisch erstellt.

Natürlich können Sie es auch in einem Lagerhaus unterbringen.

Übersetzungsskriptreferenz [run.sh](https://github.com/xxai-art/doc/blob/main/run.sh)

Der Skriptcode wird wie folgt interpretiert:

[Bunx](https://bun.sh/docs/cli/bunx) ist ein Ersatz für Npx, das schneller ist. Wenn Sie bun nicht installiert haben, können Sie natürlich stattdessen `npx` verwenden.

`bunx mdt zh` stellt `.mdt` im zh-Verzeichnis als `.md` dar, siehe die beiden verknüpften Dateien unten

* [kaffee_plus.mdt](https://github.com/xxai-doc/zh/blob/main/coffee_plus.mdt)
* [kaffee_plus.md](https://github.com/xxai-doc/zh/blob/main/coffee_plus.md)

`bunx i18n` ist der Kerncode für die Übersetzung (wenn Sie nur `nodejs` installiert haben, `bun` und `direnv` jedoch nicht installiert sind, können Sie zum Übersetzen auch `npx i18n` ausführen).

Es wird [i18n.yml](https://github.com/xxai-art/doc/blob/main/i18n.yml) analysiert. Die Konfiguration von `i18n.yml` in diesem Dokument ist wie folgt:

```
en:
zh: ja ko en
```

Die Bedeutung ist: Chinesische Übersetzung ins Japanische, Koreanische, Englische, Englische Übersetzung in alle anderen Sprachen. Wenn Sie nur Chinesisch und Englisch unterstützen möchten, können Sie einfach `zh: en` schreiben.

Der letzte ist [gen.README.coffee](https://github.com/xxai-art/doc/blob/main/gen.README.coffee) , der den Inhalt zwischen dem Haupttitel und dem ersten Untertitel der `README.md` jeder Sprache extrahiert, um einen Eintrag `README.md` zu generieren. Der Code ist sehr einfach, Sie können ihn sich selbst ansehen.

Für die kostenlose Übersetzung wird die Google API verwendet. Wenn Sie nicht auf Google zugreifen können, konfigurieren und richten Sie bitte einen Proxy ein, z. B.:

```
export https_proxy=http://127.0.0.1:7890 http_proxy=http://127.0.0.1:7890 all_proxy=socks5://127.0.0.1:7890
```

Das Übersetzungsskript generiert einen Übersetzungscache im `.i18n` Verzeichnis. Bitte überprüfen Sie ihn mit `git status` und fügen Sie ihn dem Code-Repository hinzu, um wiederholte Übersetzungen zu vermeiden.
