# Meilenstein 1

Sie sind Entwickelnde für ein Softwareunternehmen, das eine Webseitenapplikation für das Verfassen, Ändern und Verwalten von Blogartikeln umsetzen möchte. Hierfür soll der Bestandscode von Conduit verwendet werden. Conduit ist eine Beispielapplikation des [RealWorld](https://main--realworld-docs.netlify.app/)-Projektes, um verschiedene Frameworks und Programmiersprachen für eine vorher spezifizierte Applikation zu verwenden.

Für die angestrebte Webseitenapplikation Conduit wurden drei Softwareteile der Client-Server-Anwendung in Form eines Mono-Repository zusammengefasst. Diese enthalten:

- ein Backend auf Basis von ASP.Net, geschrieben in C#
- ein Frontend für Webbrowser auf Basis von Vue.js, geschrieben in Typescript
- ein Frontend für eine native Android Applikation, geschrieben Kotlin

Die drei Softwareteile sind im Unterordner `apps` zu finden. Für das Mono-Repository gibt es eine [Projekt Readme](./readme_project.md), wie das Projekt einzurichten ist.

## Zusammenfassung

Als Entwickelnde müssen Sie zunächst ein Verständnis über das Programmierprojekt erhalten. Dazu müssen Sie das Projekt in einer Entwicklungsumgebung einrichten, die grundsätzliche Funktionalität testen und für sich verständlich dokumentieren. Zudem müssen Sie sich über die wesentlichen Konzepte in den verwendeten Programmiersprachen und Frameworks vertraut machen.

Die Aufgaben sind zu erledigen und im Repository hochzuladen. Dies erfolgt durch Commits und Push via Git an das jeweilige Projekt-Repository. Die Abgabefrist ist der `01.05.2026 23:59 Uhr (MESZ)`. Der finale Commit ist mit
```[bash]
git tag abgabe-meilenstein1
```
zu taggen und im Repository mit
```[bash]
git push origin tag abgabe-meilenstein1
```
hochzuladen. Prüfen Sie im Team vor der Abgabedeadline, dass die korrekte Version getagged und hochgeladen wurde.

## Meilensteinaufgabe

1. Softwareprojekt einrichten und Lauffähigkeit testen
    - [ ] Installieren Sie das Versionierungssystem [git](https://git-scm.com/downloads) und laden Sie das Projekt auf das System herunter, in dem Sie die Applikation entwickeln wollen. 
    - [ ] Nutzen Sie die beigefügte [Projekt-ReadMe](./readme_project.md) für das Projekt, um Ihre Entwicklungsumgebung einzurichten. Testen Sie die Funktionsfähigkeit der einzelnen Komponenten (Front- und Backend), indem Sie Nutzer, Artikel und Kommentare anlegen bzw. Artikel liken und Nutzerdaten ändern.

2. Programmverständnis erzeugen
	- [ ] Nutzen Sie die jeweils die Dokumentationen der Frameworks [ASP.Net](https://learn.microsoft.com/en-us/aspnet/core/getting-started/?view=aspnetcore-8.0), [Vue.js](https://vuejs.org/guide/introduction.html) und [Kotlin](https://kotlinlang.org/docs/getting-started.html) als auch weiterführende Tutorials zu den Programmiersprachen bzw. übergeordneten Konzepten (bspw. REST-APIs, Reactive Programming u.ä.), um ein notwendiges Grundverständnis über deren Konzepte und deren Umsetzung anzueignen
	- [ ] Kommentieren Sie - entsprechend Ihrer Anforderungen - aktiv den Quellcode, um ein Verständnis über einzelne Softwarekomponenten zu erzeugen. Testen Sie dabei insbesondere folgende Anwendungsfälle
		- [ ] Konfiguration der Backend-Adressen im Backend bzw. in den jeweiligen Frontends
		- [ ] Anlegen eines neuen Nutzer über den "Sign Up"-Button in den Vue.js und Android Frontends  bis hin zum Speichern in der Datenbank
		- [ ] Anlegen eines neuen Artikels in jeweils beiden Frontends durch einen Nutzer bis zum Speichern in der Datenbank
		- [ ] Anzeigen einer Auflistung aller verfügbaren Artikel in der Datenbank in jeweils beiden Frontends
		- [ ] Ändern von Nutzerprofilen (u.a., Passwort, Nutzerbild) in jeweils beiden Frontends bis zum Speichern in der Datenbank
		- [ ] Anzeigen aller Kommentare zu einem Artikel aus der Datenbank in jeweils beiden Frontends
	- [ ] Dokumentieren Sie die wesentlichen Unterschiede zwischen den beiden Frontends beim Anlegen von Artikeln und Nutzern
3. Erstellen von Dokumentationen zur Software und deren Architektur
    - [ ] Nutzen Sie das [PlantUML](https://marketplace.visualstudio.com/items?itemName=jebbs.plantuml) um Diagramme zu erzeugen
    - [ ] Lesen Sie sich in die Syntax und Funktionsweise der [C4-Erweiterung von PlantUML](https://github.com/plantuml-stdlib/C4-PlantUML) ein. Ein Beispiel Diagramm finden sie im docs Ordner: [basic_sample.puml](docs/basic_sample.puml)
	- [ ] Erstellen Sie mit Hilfe der C4-PlantUML-Syntax **ein** Level 1 Context-Diagramm für das bestehende Gesamtsystem von Conduit. Speichern Sie das PlantUML-Modell (`*.puml`-Datei) unter `./docs/`
	- [ ] Erstellen Sie mit Hilfe der C4-PlantUML-Syntax **ein** Level 2 Container-Diagramm für das bestehende Gesamtsystem von Conduit. Speichern Sie das PlantUML-Modell (`*.puml`-Datei) unter `./docs/`
	- [ ] Erstellen Sie pro Softwarekomponente für das Backend und jeweils die beiden Frontends mit Hilfe der C4-PlantUML-Syntax **jeweils ein** Level 3 Component-Diagramm. Speichern Sie die PlantUML-Modelle (`*.puml`-Dateien) unter `./docs/`
	- [ ] Erstellen Sie für die Anwendungsfälle "Nutzer-Login" und "Artikel anlegen" (d.h. vom Frontend zum Backend) mit Hilfe der UML-Syntax für [Sequenzdiagramme in PlantUML](https://plantuml.com/de/sequence-diagram) **jeweils ein** Level 4 Code-Diagramm. Speichern Sie das PlantUML-Modell (`*.puml`-Datei) unter `./docs/`
	- [ ] 	Erstellen Sie für die Komponente "API" im Backend in ASP.Net (d.h. `./apps/dotnet/src/Api`) mit Hilfe der UML-Syntax für [Klassendiagramme in PlantUML](https://plantuml.com/de/class-diagram) **ein** Level 4 Code-Diagramm. Speichern Sie die PlantUML-Modelle (`*.puml`-Dateien) unter `./docs/`
4. Paketmanager
    - [ ] Machen Sie sich mit den verschiedenen Packetverwaltungen der drei Apps vertraut. Gehen Sie dabei insbesondere auf die folgenden Fragen ein:
      - [ ] An welcher Stelle im Projekt werden die Abhängigkeiten definiert?
      - [ ] Welche Pakete sind für die HTTP Funktionalität (Client oder Server) wichtig?
      - [ ] Wo finde Sie die Dokumentationen zu den wichtigsten Paketen?
      - [ ] Welchen Zweck haben Wildcards und Vergleichsoperatoren in den Abhängigkeiten?
      - [ ] Wo bzw. wie können Sie weitere Paketquellen (Paket-Repositories) hinzufügen?
    - [ ] Gehen Sie für die Paketverwaltung von Vue.js zusätzlich auf die folgenden Fragen ein:
      - [ ] Was ist der Unterschied zwischen `pnpm` und `npm`?
      - [ ] Welchen Zweck haben die **lock**-Dateien (in unserem Fall `pnpm-lock.yml`)?
5. Persistente Datenbank und Testdaten
	- [ ] Dokumentieren Sie, wo und wie das Backend die Datenbank und das Datenbankschema erstellt
	- [ ] Aktuell verwendet das aktuelle Conduit eine in-memory-Datenbank, die mit jedem Neustart neu erstellt und initialisiert wird. Ändern Sie dieses Verhalten, so dass die Datenbank eine SQLite-Datenbank als eine Datei `./apps/dotnet/realworld.db`-Datei vorliegt und beim Neustart die Daten aus dieser Datei persistent nutzt.
	- [ ] Um entsprechend die Applikation testen zu können, benötigen Sie Testdaten. Für belastbare Tests erstellen Sie eine entsprechend große Menge an Daten, d.h. min. 200 Artikel (den Body des Artikels in [markdown-Syntax](https://www.markdownguide.org/basic-syntax/) ca. 50-200 Wörter) von min. 20 Nutzern. Jeder Artikel sollte zwischen 3-4 Tags beinhalten. 50 Artikel sollen min. 1-5 Likes haben und 20 Artikel sollen zwischen 1-3 Kommentare haben. 5 Nutzer sollen min. 1-3 anderen Nutzern folgen.
		- Es empfiehlt sich diese Testdaten automatisch zu erzeugen. Nutzen Sie hierfür verfügbare Textgeneratoren bspw. [Lorem-Ipsum Generatoren](https://github.com/templeman/awesome-ipsum) mit einer verfügbaren REST-API.
		- Um Daten in das System einzutragen, empfiehlt es sich die REST-API des Backends zu benutzen. Das Backend bietet dabei eine Dokumentation der API als [Swagger UI](https://swagger.io/tools/swagger-ui/) an. In der Standard-Konfiguration des Backends ist die Swagger UI.
		- Nutzen Sie gerne ein Skript, um die automatisch erzeugten Daten über die REST-API in das Backend einzuspeisen. Beachten Sie, dass einige Operationen eine vorherige Autorisierung von einem Nutzer benötigen (d.h., vorheriger Login über die REST-API und Weiterverwenden des Bearer Tokens). Nutzen Sie zum Testen die Swagger UI.
		- Für einfache REST-Anfragen kann [`curl`](https://curl.se/) verwendet oder entsprechende Bibliotheken für verschiedene Programmiersprachen bspw. [requests](https://pypi.org/project/requests/) für Python, [RestSharp](https://restsharp.dev/v107/) für C# oder [`java.net`](https://mkyong.com/webservices/jax-rs/restfull-java-client-with-java-net-url/) für Java.