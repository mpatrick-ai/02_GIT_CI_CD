# Git in Verbindung mit CI/CD

## Git

- In VSC Fenster am besten immer eine einzelne Projekmappe
- Voraussetzung: Auf Github.com sollte bereits ein SSH-Key hinterlegt sein

### Lokal ein Git-Repository erstellen

1. `git init`: Lokal das Repository zu initialisieren/VersionsControlSystem in der Projektmappe hinterlegen
2. `git add .`: Fügt alle Dateien zu der gestageten Area hinzu (alle Dateien die an einen Commit angehängt werden sollen)
3. `git commit -m "initial commit"`
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

4. `git pull` um **Commits vom aktuellen Branch** zu syncen

## Branching
- Standardmäßig ist der `main` Branch immer der Ausgangspunkt
- Was sind Branches überhaupt: Unterschiedliche Zustände einer Software (z.B. ein weiteres Feature, welches sich noch in der Entwicklung befindet)

1. Auf den `main` Branch wechseln `git checkout main`
2. `git pull` um die aktuellsten Änderungen des main-Branch zu syncen (denkt dran, es können Commits nicht nur auf euren PC passieren)
3. `git checkout -b feature/<branch-name>`
4. Entwicklung (commits passieren nur auf diesem Branch)
5. `git push` pusht die Commits auf **diesen Branch**
6. Wenn die Entwicklung abgeschlossen ist, dann wird ein Merge request / Pull request erstellt, z.B. über Github.com
7. Dieser PR wird dann mit anderen Entwicklern geteilt und zum Review freigegeben
8. Wenn die Änderungen approveed wurden, dann kann dieser in den Main Branch gemerged werden
9. Nachdem ein feature-branch fertig entwickelt und gemerged wurde, sollte dieser gelöscht werden


#### Hints

- Feature sollte niemals auf ein main branch gebracht werden, ohne durch ein Review gelaufen zu sein!

## Merge Konflikte beheben
- Häufig entwickelt man in der selben Datei und läuft dann in sogenannte Merge-Konflikte
- Ausgang: feature-branch kann nicht auf main gemerged werden, da Konflikt das blockiert

### Einfachen Optionen um Merge-Koflikte zu beheben
1. lokal (in VSCode)
2. `git checkout main` und dann die letzten Änderungen mit `git pull` ziehen
3. Zurück auf feature Branch mit `git checkout <feature-branch>`
4. `git merge again`
5. Merge Konflikte beheben (`Incoming` oder `Current` Change Accepten)
6. Merge resolve pushen
7. Prüfen ob gemerged werden kann
8. Mergen