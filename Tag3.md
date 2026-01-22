# Git Workshop Tag 3

- [Teil 1: Was ist CI/CD?](#teil-1-was-ist-cicd)
  - [1.1 Übliche Schritte in CI/CD](#11-übliche-schritte-in-cicd)
  - [1.2 Automatisierung mit Github Actions](#12-automatisierung-mit-github-actions)
  - [1.3 Automatisierung der Automatisierung mit Dependabot](#13-automatisierung-der-automatisierung-mit-dependabot)
  - [1.5 Recap](#15-recap)
- [Teil 2: Exkurs Verschlüsselung (ca. 30 Minuten)](#teil-2-exkurs-verschlüsselung-ca-30-minuten)
  - [2.1 Symmetrische Verschlüsselung](#21-symmetrische-verschlüsselung)
  - [2.2 Asymmetrische Verschlüsselung](#22-asymmetrische-verschlüsselung)
- [Teil 3: Abschluss](#teil-3-abschluss)
  - [3.1 Was Ihr gelernt habt](#31-was-ihr-gelernt-habt)
  - [3.2 Wie war es?](#32-wie-war-es)
- [Teil 4: Materialien](#teil-4-materialien)
  - [4.1. Links](#41-links)
  - [4.2 Glossar](#42-glossar)



## Teil 1: Was ist CI/CD?

[Continuous Integration und Continuous Delivery](https://de.wikipedia.org/wiki/CI/CD)

CI/CD ist eine Methodik in der Softwareentwicklung, die darauf abzielt, Codeänderungen häufiger und zuverlässiger in die Produktion zu überführen. CI/CD verbessert die  Effizienz und Qualität der Softwareentwicklung durch Automatisierung und häufige, zuverlässige Deployments.

**Wozu ist das gut?**

-   **Automatisierung:** Reduziert manuelle Fehler und erhöht die Effizienz.
-   **Schnelle Rückmeldung:** Fehler werden frühzeitig erkannt und behoben.
-   **Stabile Releases:** Regelmäßige und automatisierte Deployments sorgen für konsistente Qualität.

**Früher:**

-   **Manuelle Builds und Tests:** Entwickler führten Builds und Tests manuell aus, was zeitaufwendig und fehleranfällig war.
-   **Seltene Releases:** Codeänderungen wurden in großen  Mengen integriert und selten in die Produktion überführt, was oft zu  unstabilen Releases führte. vgl. [Big Ball of Mud](https://de.wikipedia.org/wiki/Big_Ball_of_Mud)


### 1.1 Übliche Schritte in CI/CD
:arrow_forward: Video [DevOps Guide - CI/CD ](https://www.youtube.com/watch?v=YMJ_sdeDbFE) (8 Minuten)


1.  Code Commit:
    -   Entwickler pushen Codeänderungen in ein Versionskontrollsystem (z.B. Git).
2.  Continuous Integration (CI):
    -   **Build:** Der Code wird automatisch gebaut.
    -   **Unittests:** Kleine Tests, die einzelne Funktionen oder Klassen testen.
    -   **Code-Analyse:** Automatische Prüfungen auf Codequalität und Sicherheitslücken.
3.  Continuous Deployment (CD):
    -   **Integrationstests:** Testen das Zusammenspiel mehrerer Komponenten oder Systeme.
    -   **Staging Deployment:** Der Code wird in eine Staging-Umgebung deployt.
    -   **Automatisierte Tests:** Weitere Tests (End-to-End, UI-Tests) werden durchgeführt.
    -   **Produktion Deployment:** Erfolgreich getesteter Code wird automatisch in die Produktionsumgebung überführt.

### 1.2 Automatisierung mit Github Actions

Mit GitHub Actions kannst du deine Softwareentwicklungs-Workflows direkt im  Repository automatisieren, anpassen und ausführen. 

Github Actions werden in yaml geschrieben. YAML steht für *Yet Another Markup Language*. Es ist eine  für Menschen lesbare Auszeichnungssprache, die häufig für  Konfigurationsdateien verwendet wird, insbesondere von CI- und  [DevOps](https://de.wikipedia.org/wiki/DevOps)-fokussierten Softwaretools. YAML ist eine Erweiterung von JSON um syntaktisch  wichtige Zeilenumbrüche und Einrückungen, ähnlich wie auch in Python  geschrieben wird. ***Anders als in Python allerdings erlaubt YAML  keine Tabulator-Zeichen, das ist eine häufige Fehlerquelle!***

[Hier längere Erklärung zur Syntax von .yaml]

→ [Cheat Sheet YAML](https://quickref.me/yaml.html) 
→ [Cheat Sheet Github Actions](https://resources.github.com/actions/github-actions-cheat/)


**Aufgaben:**

Denkt daran, sinnvolle Commitmessages zu verwenden:
1. Baue diese [Automatisierung](https://dev.to/sre_panchanan/hello-world-in-github-actions-a-beginners-guide-to-your-first-workflow-1mbh) nach 
2. Überprüfe die Fehler in den Logs und löse sie auf bis die Action grün durchläuft. [Meine Action war von Anfang an Grün?]
3. dann [diese](https://graphite.dev/guides/github-actions-beginner-guide) [Alte main.yml Überschreiben? Detaillierte Aufgabenstellung]
4. Erweitere die Ausgabe: Wenn auf einen anderen Branch gepusht wird, soll etwas anderes im Log stehen, als wenn auf Main gepusht wird. Lege diesen anderen Branch auch an und probiere, ob es funktioniert.
5. Wenn Du Zugriff auf einen Teams-Channel hast, kannst Du dort auch eine [Nachricht hineinschreiben](https://www.indiumsoftware.com/blog/github-event-request-notification-to-teams-channel/). Wenn das nicht klappt, versucht es mit Discord oder Telegram.
6. Macht was [zeitgesteuert](https://crontab.guru/) [Bitte Aufgabenstellung detaillierter stellen]
7. Findet raus, was man mit Actions noch machen kann und erzählt uns davon.


### 1.3 Automatisierung der Automatisierung mit Dependabot
Die Warnungen in den Logs sagen, dass einige der Packages, die Ihr in den Actions benutzt habt, nicht mehr aktuell sind. Man kann das von Hand auflösen und für `/actions/checkout`im Repo [github.com/actions/checkout](https://github.com/actions/checkout) in der rechten Spalte die Versionshistory überprüfen und eine Version auswählen. Oder man lässt es machen:

[Dependabot](https://docs.github.com/de/code-security/dependabot/working-with-dependabot/keeping-your-actions-up-to-date-with-dependabot) ist ein automatisiertes Tool von GitHub, das die  Abhängigkeiten eines Projekts überwacht und automatisch Pull Requests erstellt, um diese auf die neuesten Versionen zu aktualisieren. Dependabot hilft dabei:

-   Sicherheitslücken zu schließen,  
-   die Codequalität zu verbessern und 
-   die Wartung des Projekts zu  vereinfachen, indem es sicherstellt, dass Abhängigkeiten  in der *workflow.yml*-Datei immer  aktuell  sind.

**Aufgaben:**
1. Aktiviere Dependabot Updates in Deinem Repo und lasse den Bot laufen.
2. Löse die Pull Requests auf und bringe alles auf den neusten Stand.


### 1.5 Recap
**Aufgaben:**

Schreib mit Deinen eigenen Worten in die `recap.md`:
1. Was ist CI/CD? Wozu braucht man das?
2. Was sind Github-Actions?
3. Warum Dependabot?
4. Strukturiere die Datei mit logischen Überschriften, commit und push in Dein Repo.
   

## Teil 2: Exkurs Verschlüsselung (ca. 30 Minuten)

Video [Verschlüsselung einfach erklärt](https://www.youtube.com/watch?v=yWrtCtQ7Wno) (13 Minuten)

### 2.1 Symmetrische Verschlüsselung

Bei der symmetrischen Verschlüsselung wird derselbe Schlüssel zum Ver- und Entschlüsseln von Daten verwendet.

**Vorteile:**

-   Schneller und weniger rechenintensiv
-   Einfach zu implementieren

**Nachteile:**

-   Schlüsselverteilung ist problematisch; beide Parteien müssen denselben Schlüssel sicher austauschen

**Algorithmen:**

-   AES (Advanced Encryption Standard)
-   DES (Data Encryption Standard)
-   3DES (Triple DES)

**Einsatzzwecke:**

-   Verschlüsselung von Daten während der Speicherung (z.B. auf Festplatten)
-   Sicherer Datentransfer über unsichere Netzwerke (wenn der Schlüssel sicher verteilt wurde)

### 2.2 Asymmetrische Verschlüsselung

Bei der asymmetrischen Verschlüsselung werden ein öffentlicher  Schlüssel zum Verschlüsseln und ein privater Schlüssel zum Entschlüsseln verwendet.

**Vorteile:**

-   Sicherer Schlüsselaustausch; der öffentliche Schlüssel kann frei verteilt werden
-   Ermöglicht digitale Signaturen zur Authentifizierung und Integrität

**Nachteile:**

-   Langsamer und rechenintensiver im Vergleich zur symmetrischen Verschlüsselung

**Algorithmen:**

-   [RSA](https://de.wikipedia.org/wiki/RSA-Kryptosystem) (Rivest-Shamir-Adleman)
-   ECC (Elliptic Curve Cryptography)
-   DSA (Digital Signature Algorithm)

**Einsatzzwecke:**

-   Sichere Schlüsselverteilung für symmetrische Verschlüsselung
-   Digitale Signaturen und Zertifikate
-   Sichere Kommunikation (z.B. HTTPS)



## Teil 3: Abschluss

### 3.1 Was Ihr gelernt habt

Git, Git-Config, Github, Repo, Remote, Clone und Fork, Commits und Commit-Messages, Markdown, Push, Merge, Pull vs. Fetch, add, status, log, gitignore, Branch, Pull Requests, Kanban-Board, Git GUI, SSH-Key, Git auf der Kommandozeile, YAML, CI/CD, Git Actions, workflows, Dependabot, symmetrische und asymmetrische Verschlüsselung. 

Ihr könnt ein Log lesen und Probleme selbständig lösen.

Ihr könnt zusammen arbeiten.

### 3.2 Wie war es?

Wenn Ihr den Git-Workshop für die Azubis im nächsten Jahr geben würdet – was würdet Ihr anders machen? Reihenfolge, Inhalte, mehr oder weniger von irgendwas? [Gerne mehr Aufgaben die von einem der Leiter am Screen bearbeitet werden] [ 


**Aufgaben:**
1. Überarbeitet in Zweierteams das Repo `git-Workshop` und nutzt für jede Änderung einzelne Commits mit aussagekräftigen Messages, etwa `remove Video`oder `add explanation` oder `change the order`.
2. Stellt diese Änderungen anhand der Commit-History vor.

Danke :clap:


## Teil 4: Materialien

### 4.1. Links

Videos
  - [Git in 2 Minutes with Mosh](https://www.youtube.com/watch?v=2ReR1YJrNOM)
  - [Git in 10 Minutes](https://www.youtube.com/watch?v=nCI4DxAF3Ak)
  - [Git Tutorial for Beginners](https://www.youtube.com/watch?v=8JJ101D3knE) (69 Minuten)

Buch
  - [Pro Git Buch](https://git-scm.com/book/en/v2)

Cheat Sheets
  -   [Git von GitHub](https://education.github.com/git-cheat-sheet-education.pdf)
  -   [VScode](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-macos.pdf)
  
Interaktive Git-Tutorials
-   [Git Immersion](https://gitimmersion.com/)
-   [Learn Git Branching](https://learngitbranching.js.org/?locale=de_DE)

Prüfungsvorbereitung
- [Github-Repo mit allen Inhalten für die Berufsschule](https://github.com/TredexOwl/Berufsschule)
- [Themenübersicht für die Prüfungsvorbereitung](https://fachinformatikerpruefungsvorbereitung.de/)



### 4.2 Glossar

**Branch** - ein paralleler Entwicklungszweig innerhalb eines Repositories, der es ermöglicht, unabhängig vom Hauptentwicklungsstrang zu arbeiten. Kurz gesagt ist es ein Label (ein Name) für einen Commit und dessen History.

**Checkout** - Zeitreisen zu einer bestimmten Version eines Branches.

**Clone** - das (einmalige) Kopieren eines Remote-Repositories auf den lokalen Rechner, inklusive aller Dateien, Historie und Branches.

**Commit** - ein Schnappschuss der aktuellen Änderungen, der im Repository gespeichert wird und eine eindeutige Kennung erhält.

**Fetch** - das Herunterladen von neuen Änderungen aus einem Remote-Repository, ohne diese in den aktuellen Branch zu integrieren.

**Hash** - eine eindeutige ID für Deinen Commit

**HEAD** - der Zeiger auf den aktuell aktiven Branch bzw. Commit.

**Index** - der Staging-Bereich, in dem Änderungen gesammelt werden, bevor sie committet werden.

**Merge** - das Zusammenführen von Änderungen aus verschiedenen Branches.

**Pull** - das Herunterladen und Zusammenführen von Änderungen aus einem Remote-Repository in den aktuellen Branch.

**Push** - das Hochladen von Commits aus dem lokalen Repository in ein Remote-Repository.

**Remote** - ein anderer Computer mit einem Repository.

**Repository (Repo)** - ein Ordner, der alle Dateien und die gesamte Historie der Änderungen eines Projekts enthält.

**Reset** - das Zurücksetzen des aktuellen Branches auf einen bestimmten Commit, wobei Änderungen optional verworfen oder behalten werden können.

**Staging** - der Prozess des Hinzufügens von Änderungen zum Index, um sie für den nächsten Commit vorzubereiten.

**Tag** - ein markierter Punkt in der Commit-Historie, oft verwendet, um Versionsnummern zu kennzeichnen.

**Working Directory** - das aktuelle Verzeichnis auf dem lokalen Rechner, das die Dateien des Repositories enthält und Änderungen widerspiegelt.

