# Git in Verbindung mit CI/CD

## Git

- In VSC Fenster am besten immer eine einzelne Projekmappe
- Voraussetzung: Auf Github.com sollte bereits ein SSH-Key hinterlegt sein

### Lokal ein Git-Repository erstellen

1. `git init`: Lokal das Repository zu initialisieren/VersionsControlSystem in der Projektmappe hinterlegen
2. `git add .`: Fügt alle Dateien zu der gestageten Area hinzu (alle Dateien die an einen Commit angehängt werden sollen)
3. `git commit -m `initial commit"'
4. `.gitignore` anlegen, um kontinuierlich Dateine zu verweisen die nicht getracked werden sollen

### Verknüpfung auf ein Remote-Repository

1. Remote repository erstellen auf dem Github.com Account
2. Anweisungen auf neuem Repository folgen (...push existing repository)
3. Bei den Befehlen beachten, dass Ihr SSH ausgewählt habt, dann sollte die origin url mit `git` anfangen
```bash
git remote add origin https://github.com/mpatrick-ai/02_GIT_CI_CD.git
git branch -M main
git push -u origin main
```