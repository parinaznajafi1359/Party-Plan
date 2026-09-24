# Frage: Erstelle einen neuen branch ändere etwas und pushe deine Änderungen

## 1. Schritt

`git switch -c feature/spiele`

git switch = du wechselst in den branch

-c = creat du erstellst den neuen branch

feture/spiele = der Name von dem branch


## 2. Schritt

du änderst etwas in der Text Datei

zum Beispiel du schreibst bei Spiele: Monopoly


## 3. Schritt

du speicherst deine Änderungen

`git add .`

`git commit -m "feat(spiele): monopoly"`

`git push`


## 4. Schritt

du zeigst deinen Branch

`git log --oneline --graph --all`

<br>


# Frage: Merge den branch auf main

um wieder auf den main branch zu gehen machst du das:

`git switch main`

dann kommt der merge request

`git merge feature/spiele`

`git push`

jetzt haben wir wieder nur noch einen branch

herzeigen mit:

`git log --oneline --graph --all`

<br>

# Frage: Zeige mir den Branch den jemand anderer erstellt hat

`git fetch`

`git branch -a`

<br>

# Frage: lösche den remote branch

`git fetch --prune`

`git branch -d feature/snacks`

`git branch -a `

<br>

# Frage: Was mach man mit `git rebase main`

damit kann man einen Konflikt lösen

<br>

# Frage: Was sind die 3 wege um zu pushen


`git push` = normaler push

`git push --force` = überschreibt den Branch auf GitHub bedingungslos, auch Commits, die ein anderer inzwischen gepusht hat. Sollte man nicht verwenden

`git push --force-with-lease` = überschreibt nur, wenn der Branch auf GitHub noch so aussieht wie
beim letzten Fetch. Hat inzwischen jemand gepusht, bricht Git ab.
Das ist der Push nach dem Rebase.