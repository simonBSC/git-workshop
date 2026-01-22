# Git Workshop Tag 1

- [Vorstellung](#vorstellung)
- [Teil 1: Was ist Git?](#teil-1-was-ist-git)
  - [1.1 Einführung in Versionskontrolle](#11-einführung-in-versionskontrolle)
  - [1.2 Was ist Git?](#12-was-ist-git)
  - [1.3 Was ist Git nicht?](#13-was-ist-git-nicht)
- [Teil 2: Einrichten von Git](#teil-2-einrichten-von-git)
  - [2.1 Installation von Git](#21-installation-von-git)
  - [2.2 Konfiguration von Git](#22-konfiguration-von-git)
  - [2.3 Erste Schritte mit Git](#23-erste-schritte-mit-git)
  - [2.4 GitHub](#24-github)
- [Teil 3: Grundlegende Git-Befehle](#teil-3-grundlegende-git-befehle)
  - [3.1 Lokale Änderungen](#31-lokale-änderungen)
  - [3.2 Arbeiten mit Remote-Repositories](#32-arbeiten-mit-remote-repositories)
  - [3.3 Branching](#33-branching)
  - [3.4 Merging](#34-merging)
- [Teil 4: Best Practices und Tipps](#teil-4-best-practices-und-tipps)
  - [4.1 Ordnung und Struktur](#41-ordnung-und-struktur)
  - [4.2 README.md](#42-readmemd)
  - [4.3 .gitignore](#43-gitignore)
  - [4.3 Token](#44-token)
- [Teil 5: Abschluss und Ausblick](#teil-5-abschluss-und-ausblick)
  - [5.1 Zusammenfassung](#51-zusammenfassung)
  - [5.2 Hausaufgabe](#52-hausaufgabe)


## Vorstellung
Was führt Euch her?

Wie läuft das hier? Zeiten, Duzen, Melden und Abmelden
 
## Teil 1: Was ist Git? 

### 1.1 Einführung in Versionskontrolle

Versionskontrolle ist ein System zur Verwaltung von Änderungen an Dokumenten, Code oder anderen Dateien.

Warum ist Versionskontrolle wichtig?
- Verfolgung von Änderungen: Wer hat was, wann und warum geändert?
- Rückverfolgbarkeit: Ermöglicht das Zurückkehren zu früheren Versionen.
- Zusammenarbeit: Erlaubt es mehreren Personen, gleichzeitig an einem Projekt zu arbeiten, ohne dass ihre Änderungen einander überschreiben.

### 1.2 Was ist Git?
Git ist ein Versionsmanagementsystem, entwickelt von Linus Torvalds 2005 für die Verwaltung des Linux-Kernel-Codes, das schnell, effizient und skalierbar ist. Git ist das System, das von fast allen Entwickler*innen auf der Welt benutzt wird, es ist quasi Industriestandard.
-   Dezentral: Jeder Benutzer hat eine vollständige Kopie des Repositories.
-   Snapshots: Speichert Zustände des Projekts zu verschiedenen Zeitpunkten.
-   Branching: Ermöglicht das parallele Entwickeln von Features und das spätere Zusammenführen.
-   Hashes: Commits werden über Hashes identifiziert.
-   Kostenlos: Git ist [Free und Open Source Software](https://de.wikipedia.org/wiki/Free/Libre_Open_Source_Software)

### 1.3 Was ist Git nicht?
-   Git ist kein Dateispeicher, sondern ein Werkzeug zur Verwaltung von Dateiänderungen.
-   Es ist nicht nur für Entwickler: Git kann für jede Art von Datei verwendet werden, nicht nur für Code.
-   Git ist nicht dasselbe wie GitHub: GitHub ist eine Plattform für die Zusammenarbeit mit Git-Repositories, aber Git selbst ist unabhängig davon nutzbar.
-   Git ist nicht nur für Teams: Auch Einzelpersonen können von den Vorteilen der Versionskontrolle profitieren.

## Teil 2: Einrichten von Git [Einrichtung war zu komplex, um das mit so wenig Punkten zu beschreiben]
Git ist erstmal nur ein Softwarepaket. Du kannst es benutzen über:
- die Command Line
- die Integration in Deine IDE
- oder eine extra GUI 

### 2.1 Installation von Git
Lade Git von der [offiziellen Website](https://git-scm.com/) oder verwende einen Paketmanager (z. B. apt, yum, Homebrew). Installiere Git auf Deinem Betriebssystem:
-   Windows: Ausführbares Installationsprogramm herunterladen und ausführen.
-   macOS: Installation über Homebrew, Installer oder Xcode Command Line Tools.
-   Linux: Installation über Paketmanager (z. B. apt für Ubuntu, yum für Fedora).


### 2.2 Konfiguration von Git [das war gut und hilfreich]
Konfigurieren von Benutzername und E-Mail-Adresse:
-   `git config --global user.name "Your Name"`
-   `git config --global user.email "your.email@example.com"`

Konfigurieren von Standardeditoren und anderen Optionen:
-   `git config --global core.editor "editor-name"`
-   Weitere Optionen: z. B. Farbunterstützung, Verhalten bei Konflikten.

Überprüfen der Git-Konfiguration:
-   `git config --list`: Zeigt alle globalen Einstellungen an.
-   `git config <key>`: Zeigt den Wert einer bestimmten Konfigurationsoption an.


> [!TIP]
> **Einrichten von Git in VScode** [wenn man noch nie mit git und vs code gearbeitet hat, sind die anweisungen zu schwammig, um ihnen folgen zu können]
> 
> Wenn Du in Vscode kein Source Control Menu siehst, gehe in die Settings, enable git und überprüfe, ob der Path zu git korrekt ist.



**Aufgaben:**
  1. Installiere und konfiguriere git auf Deinem Rechner.
  2. Wo liegt die Konfigurationsdatei, wie sieht die aus? 
  3. Was kann man dort noch konfigurieren? → [Cheat Sheet Git-Config](https://git-scm.com/book/de/v2/Erste-Schritte-Git-Basis-Konfiguration)


### 2.3 Erste Schritte mit Git [hilfreich, Verbesserungen: ein Repo für den ganzen Workshop, um den Überblick zu bewahren]
In Git arbeiten wir mit Repositories. Ein Git-Repository ist nichts anderes als ein Ordner, den Du mit Git verwaltest. Darin können alle Arten von Dateien sein, Bilder und ihre Versionen, Deine Abschlussarbeit oder ein Softwareprojekt. 

Initialisierung eines Ordners als Git-Repository:
-   `git init`: Macht ein Git-Repository aus dem aktuellen Verzeichnis.
  
Clonen eines vorhandenen Repositories von einem anderen Computer/Speicher:
-   `git clone <repository-url>`: Lädt ein Remote-Repository herunter und erstellt eine lokale Kopie.
-   `git clone https://[TOKEN]@github.com/[USER/Projekt]/[REPOSITORY]`: Auth. mit Token wenn das Repo nicht öffentlich ist


**Aufgaben:** 
1. Lege Dir als erstes ein Verzeichnis *workshop* für den Workshop an, in dem Du alles speicherst, was wir hier machen werden.
2. Erstelle darin einen Ordner mit dem Namen *git-workshop-doku* und mache daraus ein Git-Repo. 
3. Woran kannst Du jetzt erkennen, dass es ein Git-Repo ist?

### 2.4 GitHub
GitHub ist eine Webplattform, auf der du Git-Repositories hosten kannst, und die Funktionen für Zusammenarbeit, Code-Überprüfung, Automatisierung und Projektmanagement bietet. Github ist nur ein Anbieter [unter vielen](https://www.heise.de/tipps-tricks/GitHub-Alternativen-Die-5-besten-Seiten-4349610.html).

**Aufgaben:**
1. Gehe zu [GitHub Sign Up](https://github.com/signup) und folge den Anweisungen, um einen neuen Account zu erstellen. Nutze dafür dieselbe E-Mail-Adresse wie für die Konfiguration von Git.
2. Aktiviere 2FA -> https://github.com/settings/security
3. Hinterlege deinen Public SSH Key -> https://github.com/settings/keys
4. Mache Dich mit der Oberfläche von Github vertraut und lege Dir dort ein neues Repo an. 
5. Installiere in VScode die Extension [Github Pull Requests and Issues](https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-pull-request-github).

Man kann Repos auf zwei Arten kopieren. Beides geht auf Github auch über einen Button:
- `clone`: Beim Klonen wird eine exakte Kopie eines bestehenden Repositorys auf den lokalen Computer heruntergeladen. Diese Kopie ist direkt mit dem Original-Repository verbunden, und Änderungen können durch Pull- und Push-Befehle synchronisiert werden.
- `fork`: Ein Fork ist eine Kopie eines Repositorys, die auf einem Server (wie GitHub) erstellt wird. Diese Kopie ist unabhängig vom Original-Repository, obwohl sie davon abstammt. Ein Fork wird oft verwendet, um an einem Projekt zu arbeiten, ohne das Original zu beeinflussen. Änderungen können später durch Pull Requests ins ursprüngliche Repository eingereicht werden.

**Aufgaben:**
1. Forke das Workshop-Repo [github.com/sandrawiegard/git-workshop](https://github.com/sandrawiegard/git-workshop) in Deinen Github-Account
2. Clone das Workshop-Repo auf Deinen Computer
   


## Teil 3: Grundlegende Git-Befehle
:arrow_forward: Video [Git for Humans](https://www.youtube.com/watch?v=eWxxfttcMts) (20 Minuten) 


### 3.1 Lokale Änderungen
Commits speichern einen Schnappschuss Deines Repos zunächst lokal. Jeder Commit erhält einen Commit-Hash, der ihn eindeutig identifiziert. Entwickler können so beliebig viele Commits erstellen, um ihre Fortschritte festzuhalten, zu experimentieren oder Fehler zu beheben, ohne das zentrale Repository zu beeinflussen. Es werden aber nicht automatisch alle Dateien gespeichert, sondern nur die, die Du dafür ausgewählt hast.

Hinzufügen von Dateien zum nächsten Commit:
 -   `git add <file>`: Fügt eine bestimmte Datei zum Staging-Bereich hinzu.
 -   `git add .`: Fügt alle geänderten Dateien im Arbeitsverzeichnis zum Staging-Bereich hinzu.
 -   `git status`: Zeigt den Status des Arbeitsverzeichnisses und des Staging-Bereichs an.

Committen von Änderungen:
-   `git commit -m "Commit message"`: Speichert alle im Staging-Bereich befindlichen Änderungen in einem neuen Commit. 

Überprüfen des Commit-Verlaufs:
-   `git log`: Zeigt eine chronologische Liste aller Commits im Repository an.
-   `git log --oneline`: Zeigt eine kompakte Liste der Commit-Nachrichten an.


> [!TIP]
> **Klare und aussagekräftige Commit-Nachrichten schreiben**
> -   Beschreibe präzise, welche Änderungen der Commit enthält und warum sie vorgenommen wurden.
> -   Verwende eine aktive Sprache und einen imperativen Stil (z. B. "Add feature" statt "Added feature").
>   
> **Aufteilen von Änderungen in kleinere, zusammenhängende Commits**
> -   Teile große Änderungen in kleinere, logische Schritte auf, um die Nachvollziehbarkeit und Zusammenarbeit zu verbessern.
> -   Vermeide das Hinzufügen von nicht verwandten Änderungen in einem einzigen Commit.


**Aufgaben:**
1. Leg in Deinem Repo *git-workshop-doku* eine Datei namens *documentation.md* an und lasse Dir den Status anzeigen. 
2. Füge die Datei zum Staging-Bereich hinzu und lasse Dir wieder den Status anzeigen. Siehst Du den Unterschied zu eben?
3. Schreibe eine Commit-Message wie *add file for documentation* und commit.
4. Schau Dir die Liste der Commits an, was siehst Du da?



### 3.2 Arbeiten mit Remote-Repositories
Lokale Commits bieten somit eine flexible Arbeitsweise, bei der Entwickler ihre Arbeit absichern und strukturieren können, bevor sie die Änderungen mit dem Team teilen. Erst wenn ein Entwickler zufrieden mit seinen Änderungen ist, werden diese durch einen Push-Befehl in ein zentrales Repository, den *remote origin*, übertragen. Dieser Workflow ermöglicht eine sichere und kontrollierte Integration der Änderungen ins Hauptprojekt. Der Commit-Hash spielt hierbei eine wichtige Rolle, da er es ermöglicht, spezifische Änderungen zu referenzieren und zurückzuverfolgen. 

Verbindung zu einem Remote-Repository herstellen:
-   `git remote add origin <repository-url>`: Verknüpft das lokale Repository mit einem Remote-Repository.

Pushen von Commits auf ein Remote-Repository:
-   `git push origin <branch-name>`: Überträgt lokale Commits auf den angegebenen Remote-Branch.

Pullen von Änderungen aus einem Remote-Repository:
-   `git pull origin <branch-name>`: Aktualisiert das lokale Repository mit den neuesten Änderungen aus dem Remote-Repository.


> [!TIP]
> **Häufiges Pushen von Commits**
> -   Lade regelmäßig Commits auf das Remote-Repository hoch, um den Fortschritt zu sichern und mit anderen zu teilen.
> -   Vermeide lange Phasen ohne Pushes, um Datenverluste zu vermeiden.
>   
> **Beachten von Änderungen im Remote-Repository vor dem Pushen**
> -   Überprüfe vor dem Pushen, ob es im Remote-Repository Änderungen gibt, die mit den lokalen Commits in Konflikt stehen könnten.
> -   Löse eventuelle Konflikte lokal, bevor du deine Änderungen pushst.



**Aufgabe:** 
1. Finde heraus, was der Unterschied zwischen `fetch`und `pull`ist.
2. Hat irgendwas nicht sofort geklappt? Schreib in *documentation.md*, was das war, und wie Du es gelöst hast. 
3. Lass Dir nach dem commit noch einmal alle auflisten und pushe sie dann.


### 3.3 Branching
Ein Branch ist ein paralleler Entwicklungszweig innerhalb eines Repositories, der es ermöglicht, unabhängig vom Hauptentwicklungsstrang zu arbeiten. Der Hauptbranch heißt *main*.

Erstellen und Wechseln zwischen Branches:
-   `git branch <branch-name>`: Erstellt einen neuen Branch.
-   `git checkout <branch-name>`: Wechselt zum angegebenen Branch.

> [!TIP]
> **Sinnvolle Nutzung von Branches**
> -   Verwende Branches, um neue Features zu entwickeln, Bugfixes vorzunehmen oder Experimente durchzuführen.
> -   Halte Branches klein und fokussiert, um Konflikte und Probleme zu minimieren.
>
> **Benennungskonventionen für Branches**
> -   Verwende aussagekräftige Namen, die den Zweck des Branches beschreiben.
> -   Gängige Konventionen umfassen Feature-Branches (z. B. `feature/new-login-page`) oder Bugfix-Branches (z. B. `bugfix/fix-404-error`).

**Aufgaben:**
1. Erstelle einen Branch mit dem Namen *testbranch*.
2. Wechsle in den Testbranch und ändere etwas an der *documentation.md*. Commit und push.


### 3.4 Merging

Zusammenführen von Branches:
-   `git merge <branch-name>`: Führt die Änderungen aus einem anderen Branch in den aktuellen Branch zusammen.

> [!TIP]
> **Vermeidung von Merge-Konflikten durch regelmäßiges Zusammenführen von Branches**
> -   Integriere Änderungen aus dem Haupt-Branch regelmäßig in Feature-Branches, um Konflikte frühzeitig zu erkennen und zu lösen.
> -   Vermeide lange Phasen isolierter Entwicklung, um die Wahrscheinlichkeit von Konflikten zu reduzieren.
>   
> **Strategien zur Konfliktlösung**
> -   Analysiere die Konflikte und verstehe die Ursachen, bevor du mit der Lösung beginnst.
> -   Kommuniziere mit anderen Teammitgliedern, um Konflikte gemeinsam zu lösen.
> 
> **Auflösen von Merge-Konflikten**
> -   Bei Konflikten müssen die Dateien manuell bearbeitet werden, um die Konflikte aufzulösen.
> -   Anschließend wird der Commit abgeschlossen, um den Merge abzuschließen.

**Aufgaben:** 
1. Dann wechsle nach *main* und merge *testbranch*in den *main*.
2. Schau Dir jetzt die History von *main*an.
3. Hat irgendwas nicht sofort geklappt? Schreib in *documentation.md*, was das war, und wie Du es gelöst hast. Dann commit und push.


## Teil 4: Best Practices und Tipps

### 4.1 Ordnung und Struktur
**Namenskonventionen für Branches**

Gängige Konventionen umfassen Feature-Branches (z. B. `feature/new-login-page`) oder Bugfix-Branches (z. B. `bugfix/fix-404-error`)

[Convention over Configuration](https://de.wikipedia.org/wiki/Konvention_vor_Konfiguration) ist ein Softwareentwicklungsprinzip, das darauf abzielt, die Komplexität von Systemen zu reduzieren, indem vorgegebene Konventionen genutzt werden, um gängige Aufgaben ohne umfangreiche Konfigurationen zu lösen. 


### 4.2 README.md
Das was in Github auf der Startseite jedes Repos zu sehen ist, ist die README.md. Was darin stehen sollte, erfahrt Ihr hier: https://oer-informatik.de/git04-readme-erstellen.

Das `.md` steht für Markdown, eine Auszeichnungssprache, die als HTML angezeigt wird. Sie ist ganz einfach zu benutzen. → [Markdown Cheat Sheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).

Auf Github, also im *Github-flavoured* Markdown können auch [Emojis verwendet](https://gist.github.com/rxaviers/7360908) werden. :scream:

**Aufgaben:**
1. Erstelle eine sinnvolle README.md für Dein Repo *git-workshop-doku* mit Überschriften, einem Link zum Repo *git-workshop* und einem Text, der Dich auch in einem Jahr noch daran erinnert, was in diesem Repo zu finden ist.
2. Commit und push die README in Dein remote Repo auf Github.


### 4.3 .gitignore
Eine `.gitignore`-Datei ist eine einfache Datei in einem Git-Repository, die festlegt, welche Dateien und Verzeichnisse Git ignorieren soll. Diese Dateien werden weder verfolgt noch versioniert, wodurch unnötige oder sensible Daten aus dem Versionskontrollsystem ausgeschlossen bleiben. Typische Inhalte sind beispielsweise temporäre Dateien, Build-Artefakte, persönliche Konfigurationsdateien und andere nicht relevante Dateien für das Projekt. 

→ [Cheat Sheet .gitignore](https://github.com/kenmueller/gitignore)

### 4.4 Token 
Um sich an nicht-öffentlichen Repos zu authentifizieren, sollte ein Token verwendet werden.
Anders als ein User/PW erlangt jemand bei einem Leak des Token keine Kontrolle über den Git Account.
Ein Token in z.B. Github erstellt man über Einstellungen->Developer Settings->Personal Access Token. Dort wählt man aus, welche Rechte bei einem Zugriff vorliegen.
Beispiel des Klonens: `git clone https://[TOKEN]@github.com/[USER/Projekt]/[REPOSITORY]`
Die URL https://[TOKEN]@github.com/[USER/Projekt]/[REPOSITORY] kann auch über Git Plugins/Addons in den IDEs bei der Angabe der Remote URL angegeben werden

**Aufgaben:**
Erstelle eine Datei mit dem Namen `.gitignore` im Root Deines Repos und schließe dort beispielhaft aus:
- Dateien mit der Endung `txt`
- Systemdateien wie `.env` und `.venv`
- den Inhalt eines Ordners mit dem Namen `logs`
- dann check die Datei ein


## Teil 5: Abschluss und Ausblick

### 5.1 Zusammenfassung
**Aufgaben:**
1. Lege in Deinem Repo eine Datei `recap.md`an und schreibe die fünf Vorteile von Git auf. Benutze eine Liste in Markdown dafür.
2. Committe mit einer aussagekräftigen Message und pushe in Dein Github-Repo.


### 5.2 Hausaufgabe
**Aufgaben:**
1. Suche im Internet nach GUIs für Git.
2. Welches GUI für Git gefällt Dir und warum?
3. Schreib es mit Link und Screenshot in die `recap.md`, commit und push.
