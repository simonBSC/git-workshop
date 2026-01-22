# Git Workshop Tag 2

- [Teil 1: Weitere Git-Funktionen](#teil-1-weitere-git-funktionen)
  - [1.1 Pull Requests](#11-pull-requests)
  - [1.2 Squashen](#12-squashen)
  - [1.3 Rebasen](#13-rebasen)
- [Teil 2: Recap Git](#teil-2-recap-git)
  - [2.1 Git Video](#21-git-video)
  - [2.2 Git GUI](#22-git-gui)
  - [2.3 Git-Quiz](#23-git-quiz)
- [Teil 3: Warum es gut ist, sich auf der Shell zurechtzufinden](#teil-3-warum-es-gut-ist-sich-auf-der-shell-zurechtzufinden)
  - [3.1 Installation Starship Cross-Shell-Prompt](#31-installation-starship-cross-shell-prompt)
  - [3.2 Git Übungen auf der Shell](#32-git-übungen-auf-der-shell)
- [Teil 4: SSH-Key erstellen und in Deinem Github-Account hinterlegen](#teil-4-ssh-key-erstellen-und-in-deinem-github-account-hinterlegen)
  - [4.1 Vorteile der Nutzung von GitHub über SSH](#41-vorteile-der-nutzung-von-github-über-ssh)
  - [4.2 Einrichtung von GitHub über SSH](#42-einrichtung-von-github-über-ssh)


## Teil 1: Weitere Git-Funktionen
[Max]

### 1.1 Pull Requests 


### 1.2 Squashen
Wenn Ihr Euch die Commit-History mit `git log` [haben wir nicht verstanden bzw undeutlich erklärt]

### 1.3 Rebasen
rebase vs merge


## Teil 2: Recap Git

### 2.1 Git Video
:arrow_forward: Video [Git happens](https://www.youtube.com/watch?v=yCh6TSLIQBQ) (37 Minuten) [Eine Erläuterung, worum es genau in dem Video geht oder eine Nachbesprechung danach wäre hilfreich gewesen]

### 2.2 Git GUI
Hausaufgaben vergleichen:
Welche GUI für Git gefällt Dir und warum? Zeig her. [Wir hätten es besser gefunden, wenn uns vorher eine Git GUI gezeigt worden wäre, anstatt uns das selber beizubringen]

### 2.3 Git-Quiz
https://www.w3schools.com/quiztest/quiztest.asp?qtest=GIT



## Teil 3: Warum es gut ist, sich auf der Shell zurechtzufinden

Die Shell ist ein unverzichtbares Werkzeug für Entwickler und Systemadministratoren, weil sie direkten Zugriff auf das Betriebssystem und die damit verbundenen Ressourcen bietet. Diese Fähigkeiten können die Problemlösungsfähigkeiten und das Verständnis für Computersysteme erheblich verbessern.

Die Shell ermöglicht es, Aufgaben effizient und automatisiert zu erledigen, was die Produktivität erheblich steigern kann. Durch das Erlernen von Shell-Kommandos und Skripten können komplexe Prozesse vereinfacht und wiederholbare Aufgaben automatisiert werden.


### 3.1 Installation Starship Cross-Shell-Prompt
Der Prompt kann verschiedene Informationen anzeigen, die für den aktuellen Kontext relevant sind, wie Git-Status, Node.js-Versionen, Docker-Status, und vieles mehr. Dies hilft, wichtige Informationen auf einen Blick zu sehen, ohne zusätzliche Befehle eingeben zu müssen.

[Starship CMD](https://github.com/starship/starship/blob/master/docs/de-DE/guide/README.md) installieren.

[Um Schriftarten einzupflegen braucht man Windows Terminal, mit PowerShell selbst geht das nicht. (Windows Terminal fasst die PowerShell und andere Kommandozeilen in eine zusammen.)
Windows Terminal ist eine Anwendung von Microsoft, von der PowerShell, CMD und alle anderen Eingabeaufforderungen unter Windows überschrieben werden. 
Hier kann man unter anderem direkt die Schriftart ändern und hat die Möglichkeit die Farben anzupassen und ein Hintergrundbild einzufügen.]

### 3.2 Git Übungen auf der Shell
https://lerneprogrammieren.de/git/ [diese Befehle hätten wir lieber am Anfang gelernt oder an Tag 1]



## Teil 4: SSH-Key erstellen und in Deinem Github-Account hinterlegen [Ein Tutorial zum Erstellen dieses Keys hätten wir sehr begrüßt.]

### 4.1 Vorteile der Nutzung von GitHub über SSH

1.  **Sicherheit:** SSH bietet eine sichere Methode zur Authentifizierung und Verbindung mit GitHub, indem es verschlüsselte Verbindungen verwendet.
2.  **Komfort:** Einmal eingerichtet, ermöglicht SSH eine Authentifizierung ohne Kennwort oder Token, was die Nutzung von Git-Operationen schneller und bequemer macht.
3.  **Automatisierung:** SSH-Schlüssel sind ideal für automatisierte Skripte und CI/CD-Pipelines, da sie ohne Benutzereingriffe funktionieren.


### 4.2 Einrichtung von GitHub über SSH
https://jdblischak.github.io/2014-09-18-chicago/novice/git/05-sshkeys.html

**Aufgaben:**
1.   Hinterlege bei Github Deinen SSH-Key
2.   Lass Dir anzeigen, welche remote origins Dein Repo hat: `git remote -v`
3.   Ändere den remote origin auf die ssh-URL Deines Repos bei Gitub: `git remote set-url origin [ssh-URl deines Repos]`
