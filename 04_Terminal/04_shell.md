```text
Linux Terminal – Grundlagen (Nano- / Vim-Format)
==============================================

1. Terminal & Shell – Grundverständnis
-------------------------------------
Terminal = Textoberfläche
Shell    = Befehlsinterpreter (meist bash)

- Terminal ist das Werkzeug
- Shell führt Befehle aus
- CLI: schneller, skriptfähig, server-tauglich

2. Aufbau eines Befehls
----------------------
Syntax:
befehl [optionen] [argumente]

Beispiele:
ls -l /etc
cp -r dir1 dir2
- Optionen: ändern Verhalten (-l, -a)
- Argumente: Ziel oder Quelle
Merksatz:
Befehl sagt WAS, Option sagt WIE, Argument sagt WO.

3. Navigation im Dateisystem
----------------------------
pwd        # zeigt aktuelles Verzeichnis
ls         # listet Inhalte (Dateien/Ordner)
ls -la     # detailliert + versteckte Dateien (.)
cd /pfad   # wechselt in /pfad
cd ..      # eine Ebene hoch
cd ~       # ins Home-Verzeichnis

Merksatz:
pwd = wo bin ich, ls = was ist da, cd = wohin gehe ich.

4. Dateien & Ordner verwalten
-----------------------------
touch file.txt        # erstellt leere Datei / aktualisiert Zeitstempel
mkdir dir             # erstellt Ordner
mkdir -p a/b/c        # erstellt Ordnerstruktur inkl. Elternordner
cp src dst            # kopiert Datei/Ordner (Ordner mit -r)
mv alt neu            # verschiebt oder benennt um
rm file               # löscht Datei
rm -r dir             # löscht Ordner rekursiv
rm -rf dir            # erzwingt Löschen ohne Rückfrage (GEFÄHRLICH)

Merksatz:
rm -rf denkt nicht – du musst denken.

5. Dateien anzeigen & bearbeiten
--------------------------------
cat file              # zeigt Datei komplett
less file             # seitenweise Anzeige (q = exit)
head file             # Anfang (Standard: 10 Zeilen)
tail file             # Ende (Standard: 10 Zeilen)
tail -f logfile       # folgt Logdatei live
nano file             # Editor nano
vim file              # Editor vim (fortgeschritten)

Merksatz:
less ist mehr als cat.

6. Suchen & Finden
------------------
find /pfad -name "*.md"   # sucht Dateien nach Namen
grep wort file            # sucht "wort" in Datei
grep -R wort /pfad        # rekursive Inhaltssuche

Merksatz:
find sucht Dateien, grep sucht Inhalte.

7. Pipes & Umleitungen
----------------------
|    # Pipe: Ausgabe von A → Eingabe von B
>    # schreibt Ausgabe in Datei (überschreibt)
>>   # schreibt Ausgabe in Datei (anhängen)

Beispiele:
ls | grep md
dmesg | less
echo test > file

Merksatz:
Pipes verbinden Befehle wie Rohre.

8. Rechte & Besitzer
--------------------
ls -l                  # zeigt Rechte, Besitzer, Gruppe
chmod 644 file         # setzt Rechte (rw-r--r--)
chmod +x script.sh    # macht Datei ausführbar
chown user:gruppe file # ändert Besitzer und Gruppe

Rechte:
r = lesen   w = schreiben   x = ausführen

Merksatz:
Ohne x läuft nichts.

9. Benutzer & sudo
------------------
whoami       # aktueller Benutzer
id           # UID/GIDs und Gruppen
su           # Benutzer wechseln
sudo befehl  # Befehl mit Adminrechten

Hinweis:
- sudo = temporäre Root-Rechte
- niemals dauerhaft als root arbeiten

10. Prozesse & System
---------------------
ps aux      # laufende Prozesse (alle Benutzer)
top / htop  # Live-Prozessübersicht
kill PID    # beendet Prozess (Standard: TERM)
uptime      # Laufzeit + Load
free -h     # RAM / Swap
df -h       # Plattenplatz
du -sh *    # Ordnergrößen im aktuellen Verzeichnis

Merksatz:
Prozesse fressen Ressourcen – beobachte sie.

11. Paketmanagement (Grundlage)
-------------------------------
pacman -S paket     # Arch
pacman -R paket
apt install paket   # Debian / Ubuntu
dnf install paket   # Fedora / RHEL

Merksatz:
Der Paketmanager hält dein System sauber.

12. Hilfe & Lernen
------------------
man befehl        # Handbuch
befehl --help     # Kurzinfo
apropos wort      # Manpage-Suche
history           # Befehlsverlauf

Merksatz:
man weiß mehr als Google.

13. Wichtige Admin-Gewohnheiten
-------------------------------
- Befehle vor Enter lesen
- rm -rf doppelt prüfen
- Logs prüfen: /var/log
- Verstehen statt Auswendiglernen
  
``