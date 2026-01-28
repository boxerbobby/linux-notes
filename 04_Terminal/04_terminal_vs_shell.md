TERMINAL VS. SHELL
aus Sicht eines Linux-Administrators, einfach aber korrekt)


TERMINAL
--------

Was es ist:
Ein Terminal ist nur das Fenster / die Oberfläche, in die du Text eintippst
und Ausgaben siehst.

Aufgabe:
- Eingaben anzeigen
- Ausgaben anzeigen
- Tastatur -> Programm
- Programm -> Bildschirm

Beispiele:
- GNOME Terminal
- Konsole (KDE)
- Alacritty
- TTY (Strg+Alt+F2)

Das Terminal denkt nicht. Es leitet nur weiter.


SHELL
-----

Was sie ist:
Die Shell ist das Programm, das deine Befehle versteht und ausführt.

Aufgabe:
- Befehle interpretieren (ls, cd, pacman)
- Programme starten
- Variablen, Pipes, Redirects verarbeiten
- Skripte ausführen

Beispiele:
- bash
- zsh
- fish
- sh

Die Shell arbeitet.


ZUSAMMENSPIEL (WICHTIG)
----------------------

Tastatur
  |
  v
Terminal (Fenster)
  |
  v
Shell (interpretiert)
  |
  v
Linux Kernel / Programme
  |
  ^
Ausgabe zurück ins Terminal


KURZVERGLEICH
------------

Terminal:
- Oberfläche
- Zeigt Text
- Kann nichts alleine
- Austauschbar

Shell:
- Programm
- Versteht Befehle
- Führt alles aus
- Austauschbar


PRAXISBEISPIEL
--------------

Du tippst:
ls -l /etc

Ablauf:
- Terminal: zeigt, was du tippst
- Shell: versteht den Befehl und startet ls
- Kernel: liefert die Dateiliste
- Shell: gibt die Ausgabe zurück
- Terminal: zeigt sie an


MERKSATZ (ADMIN-TAUGLICH)
------------------------

Terminal ist der Bildschirm.
Die Shell ist das Gehirn.
