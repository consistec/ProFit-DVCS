* Allgemeine Hinweise
   * Für die Praxisübung haben wir bei http://www.github.com einen gemeinsamen Account angelegt
       Username: profitdvcs
       Passwort: profit2.0
   * In der Shell bekommen Sie mittels "git Kommando --help" (z.B. git commit --help) Hilfe zu allen Git Kommandos
   * In der Shell steht Ihnen für Git Kommandos Tab-Completion zur Verfügung

* Starten Sie eine Git-Bash Shell

  Doppelklick auf \Portable Git\git-bash.bat auf dem USB-Stick


* Konfigurieren Sie Ihren Nutzernamen, damit wir nachher Commits der Teilnehmer auseinander halten können
   git config --global user.name "Max Mustermann"
   git config --global user.email max@mustermann.de

* Clonen Sie das Beispielrepository
   cd projects
   git clone git@github.com:dirkl/ProFit-DVCS.git
   cd ProFit-DVCS

==================

* Zusätzlich zum Zugriff über Git, können Sie unser Git-Repository auch auf Github im Browser anschauen: https://github.com/dirkl/ProFit-DVCS

* Im Repository finden Sie zwei HTML-Dateien:

   * Readme.html
   * Template.html

* Ziel dieser Praxisübung ist, für Ihre Gruppe aus Template.html eine eigene HTML-Datei GruppeX.html zu erstellen, zum Repository in einem eigenen Branch hinzuzufügen und wieder in den Master-Branch zu integrieren

* Checkliste

   * Checken Sie den Master Branch aus
      * git checkout master
      * Überprüfen Sie das Ergebnis in der Kommandozeile (git status) und in Gitk
   * Erstellen Sie einen Branch GruppeX für die Arbeiten an Ihrer Datei (git branch GruppeX)
      * Wechseln Sie auf den neu erstellten Branch (git checkout GruppeX)
      * Sie können diese beiden Kommandos auch in einem Schritt ausführen (git checkout -b GruppeX)
   * Erstellen Sie eine Kopie GruppeX.html von Template.html und fügen Sie diese dem Repository hinzu
      * Kopieren in Explorer oder Shell
      * Aufnahme in den Index: git add Dateiname
      * Committen Sie den initialen Dateizustand
   * Editieren Sie GruppeX.html (z.B. mit Wordpad oder in der Shell)
      * Fügen Sie Ihren Namen ein und führen Sie nach Belieben weitere Änderungen durch
   * Hotfix
      * Wir möchten an dieser Stelle den typischen Fall durchspielen, dass während der Entwicklung eines Features ein kritischer Bug auftritt. Dieser muss natürlich sofort gefixt werden und Ihre aktuelle Arbeit muss beiseite gelegt werden.
      * Überlegen Sie kurz, wie Sie das in Subversion umsetzen würden.
      * In Git bietet sich für diese Situation die Nutzung des Stash an; zur Erinnerung: auf dem Stash können Sie Änderungen ohne expliziten Commit ablegen (git stash) und später wieder herstellen (git stash pop)
      	 * Packen Sie Ihre aktuellen Änderungen auf den Stash und schauen Sie sich die Situation in gitk an
	 * Checken Sie den Produktivbranch "Customer" aus
	 * Beheben Sie den fehlerhaften Link in Readme.html auf die Grafik
	 * committen Sie Ihren Bugfix
	 * Normalerweise würden Sie an dieser Stelle den Bugfix auch in das zentrale Repository pushen; das lassen wir in der Übung weg, da es unvermeidlich zu Merge-Konflikten zwischen den einzelnen Gruppen käme (jede Gruppe behebt den gleichen Fehler)
      * Der akute Fehler wurde behoben und Sie können sich wieder der ursprünglichen Aufgabe zuwenden
         * wechseln Sie zurück auf Ihren Branch: git checkout GruppeX
	 * Sehen Sie sich die HTML-Datei im Editor an: Ihre gestashten Änderungen sind nicht enthalten
	 * Holen Sie die Änderungen vom Stash: git stash pop
	 * Nun entspricht die HTML-Datei im Working-Directory wieder dem letzten Stand bevor Sie den Fehler beheben mussten
	 * Schließen Sie Ihre Änderungen ab und committen Sie
   * Integrieren Sie Ihre Änderungen in den master Branch
      * Wechseln Sie auf den master Branch (git checkout master)
      * Integrieren Sie Ihre Änderungen (git merge GruppeX)
      * Schauen Sie sich das Ergebnis in gitk an
   * Senden Sie Ihre Arbeit zum Server
      * Da auch die anderen Gruppen auf diesem Branch aktiv sind, sollten Sie zunächst Ihr Repository noch einmal mit dem Server synchronisieren
         * Beziehen Sie Änderungen vom Server: git fetch
	 * Falls es Änderungen gab, integrieren Sie diese mit Ihren Änderungen: git merge origin/master
      * Senden Sie Ihren Stand an den Server
         * git push
         

