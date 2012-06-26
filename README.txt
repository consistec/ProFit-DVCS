* Allgemeine Hinweise
   * F�r die Praxis�bung haben wir bei http://www.github.com einen gemeinsamen Account angelegt
       Username: profitdvcs
       Passwort: profit2.0
   * In der Shell bekommen Sie mittels "git Kommando --help" (z.B. git commit --help) Hilfe zu allen Git Kommandos
   * In der Shell steht Ihnen f�r Git Kommandos Tab-Completion zur Verf�gung

* Starten Sie eine Git-Bash Shell

  Doppelklick auf \Portable Git\git-bash.bat auf dem USB-Stick


* Konfigurieren Sie Ihren Nutzernamen, damit wir nachher Commits der Teilnehmer auseinander halten k�nnen
   git config --global user.name "Max Mustermann"
   git config --global user.email max@mustermann.de

* Clonen Sie das Beispielrepository
   cd projects
   git clone git@github.com:dirkl/ProFit-DVCS.git
   cd ProFit-DVCS

==================

* Zus�tzlich zum Zugriff �ber Git, k�nnen Sie unser Git-Repository auch auf Github im Browser anschauen: https://github.com/dirkl/ProFit-DVCS

* Im Repository finden Sie zwei HTML-Dateien:

   * Readme.html
   * Template.html

* Ziel dieser Praxis�bung ist, f�r Ihre Gruppe aus Template.html eine eigene HTML-Datei GruppeX.html zu erstellen, zum Repository in einem eigenen Branch hinzuzuf�gen und wieder in den Master-Branch zu integrieren

* Checkliste

   * Checken Sie den Master Branch aus
      * git checkout master
      * �berpr�fen Sie das Ergebnis in der Kommandozeile (git status) und in Gitk
   * Erstellen Sie einen Branch GruppeX f�r die Arbeiten an Ihrer Datei (git branch GruppeX)
      * Wechseln Sie auf den neu erstellten Branch (git checkout GruppeX)
      * Sie k�nnen diese beiden Kommandos auch in einem Schritt ausf�hren (git checkout -b GruppeX)
   * Erstellen Sie eine Kopie GruppeX.html von Template.html und f�gen Sie diese dem Repository hinzu
      * Kopieren in Explorer oder Shell
      * Aufnahme in den Index: git add Dateiname
      * Committen Sie den initialen Dateizustand
   * Editieren Sie GruppeX.html (z.B. mit Wordpad oder in der Shell)
      * F�gen Sie Ihren Namen ein und f�hren Sie nach Belieben weitere �nderungen durch
   * Hotfix
      * Wir m�chten an dieser Stelle den typischen Fall durchspielen, dass w�hrend der Entwicklung eines Features ein kritischer Bug auftritt. Dieser muss nat�rlich sofort gefixt werden und Ihre aktuelle Arbeit muss beiseite gelegt werden.
      * �berlegen Sie kurz, wie Sie das in Subversion umsetzen w�rden.
      * In Git bietet sich f�r diese Situation die Nutzung des Stash an; zur Erinnerung: auf dem Stash k�nnen Sie �nderungen ohne expliziten Commit ablegen (git stash) und sp�ter wieder herstellen (git stash pop)
      	 * Packen Sie Ihre aktuellen �nderungen auf den Stash und schauen Sie sich die Situation in gitk an
	 * Checken Sie den Produktivbranch "Customer" aus
	 * Beheben Sie den fehlerhaften Link in Readme.html auf die Grafik
	 * committen Sie Ihren Bugfix
	 * Normalerweise w�rden Sie an dieser Stelle den Bugfix auch in das zentrale Repository pushen; das lassen wir in der �bung weg, da es unvermeidlich zu Merge-Konflikten zwischen den einzelnen Gruppen k�me (jede Gruppe behebt den gleichen Fehler)
      * Der akute Fehler wurde behoben und Sie k�nnen sich wieder der urspr�nglichen Aufgabe zuwenden
         * wechseln Sie zur�ck auf Ihren Branch: git checkout GruppeX
	 * Sehen Sie sich die HTML-Datei im Editor an: Ihre gestashten �nderungen sind nicht enthalten
	 * Holen Sie die �nderungen vom Stash: git stash pop
	 * Nun entspricht die HTML-Datei im Working-Directory wieder dem letzten Stand bevor Sie den Fehler beheben mussten
	 * Schlie�en Sie Ihre �nderungen ab und committen Sie
   * Integrieren Sie Ihre �nderungen in den master Branch
      * Wechseln Sie auf den master Branch (git checkout master)
      * Integrieren Sie Ihre �nderungen (git merge GruppeX)
      * Schauen Sie sich das Ergebnis in gitk an
   * Senden Sie Ihre Arbeit zum Server
      * Da auch die anderen Gruppen auf diesem Branch aktiv sind, sollten Sie zun�chst Ihr Repository noch einmal mit dem Server synchronisieren
         * Beziehen Sie �nderungen vom Server: git fetch
	 * Falls es �nderungen gab, integrieren Sie diese mit Ihren �nderungen: git merge origin/master
      * Senden Sie Ihren Stand an den Server
         * git push
         

