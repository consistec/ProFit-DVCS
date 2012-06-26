Grundlegende Infos
   * F�r die Praxis�bung haben wir bei http://www.github.com einen gemeinsamen Account angelegt
       Username: profitdvcs
       Passwort: profit2.0

* Starten Sie eine Git-Bash Shell

  Doppelklick auf \Portable Git\git-bash.bat auf dem USB-Stick

* Hilfe zu allen Git Kommandos bekommen Sie mittels "git Kommando --help" (z.B. git commit --help)

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
   * Erstellen Sie eine Kopie GruppeX.html von Template.html und f�gen Sie diese dem Repository hinzu
      * Kopieren in Explorer oder Shell
      * Aufnahme in den Index: git add Dateiname
      * Committen Sie den initialen Dateizustand
   * Editieren Sie GruppeX.html (z.B. mit Wordpad oder in der Shell)
      * F�gen Sie Ihren Namen ein und TODO
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
         * 

