# Frage: Erstelle einen neuen branch ändere etwas und pushe deine Änderungen

## 1. Schritt

`git pull`

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

# Frage: Merge den branch auf main (Lokales mergen mit fast forward)

um wieder auf den main branch zu gehen machst du das:

`git switch main`

dann kommt der merge request

`git merge feature/spiele`

`git push`

jetzt haben wir wieder nur noch einen branch

herzeigen mit:

`git log --oneline --graph --all`

<br>

# Frage: Mergen über Review mit Github

Merge wird eigentlich nicht so ausgeführt sonder über eine Review in Github

Nach deinem push erscheint auf github der Button „Compare & pull request“

Hier sollte ein Vorgesetzter den push reviewen und gibt ihn frei wenn alles passt und dien branch wird gemerched

<br>

# Frage: Zeige mir den Branch den jemand anderer erstellt hat

`git fetch`

`git branch -a`

<br>

# Frage: lösche den remote branch

`git switch main`

`git pull` = den Merge holen

`git branch -d feature/login` = lokalen Branch löschen

`git fetch --prune` = veraltete Remote-Referenzen entfernen

`git branch -a`

<br>

# Frage: Wie nimmt man einen commit zurück und as ist der unterschied zwischen --hard und --soft

commits zurück nehmen funktioniert nur wenn sie noch nicht gepusht werden

`git reset --soft` = Der Commit wird zurück genommen aber bleibt gestaged

`git reset --hard` = Der Commit wird komplett zurück genommen alle nicht gespeicherten änderungen werden gelöscht

<br>

# Frage: Was bedeuted tracked, untracked und ignored?

tracked = die Datei ist in mindestens einem Commit, Git beobachtet jede Änderung

untracked = Git sieht die Datei, verwaltet sie aber nicht  also eine neue Datei die noch nie ge-add-et wurde

irgnored = sie steht im .gitignore drinnen

<br>

# Frage: Was mach man mit `git rebase main`

Wenn man an einem Projekt arbeitet auf einem brach aber der main branch ist in der zwischen zeit weiter gewachsen muss man ein rebase machen

`git fetch origin`

`git switch feature/payment`

`git rebase origin/main`

Wenn es einen Konflikt gibt hält Git an dann muss man die Dateien öffnen und sich die unterschiede anschauen und den Konflikt händisch lösen.

<br>

# Frage: Was sind die 3 wege um zu pushen

`git push` = normaler push

`git push --force` = überschreibt den Branch auf GitHub bedingungslos, auch Commits, die ein anderer inzwischen gepusht hat. Sollte man nicht verwenden

`git push --force-with-lease` = überschreibt nur, wenn der Branch auf GitHub noch so aussieht wie
beim letzten Fetch. Hat inzwischen jemand gepusht, bricht Git ab.
Das ist der Push nach dem Rebase.