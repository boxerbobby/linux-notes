# Linux Terminal – Grundlagen (Nano-Format)

## 1. Terminal & Shell – Grundverständnis
Terminal = Textoberfläche  
Shell = Befehlsinterpreter (meist bash)

- Terminal ist das Werkzeug
- Shell führt Befehle aus
- CLI ist schneller, skriptfähig, server-tauglich

Merksatz:
Terminal ist das Fenster – die Shell denkt für dich.

2. Aufbau eines Befehls
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
pwd        # aktuelles Verzeichnis
ls         # Inhalt anzeigen
ls -la     # detailliert + versteckte Dateien
cd /pfad   # wechseln
cd ..      # eine Ebene hoch
cd ~       # Home-Verzeichnis

Merksatz:
pwd wo bin ich, ls was ist da, cd wohin gehe ich.

4. Dateien & Ordner verwalten
touch file.txt        # Datei erstellen
mkdir dir             # Ordner erstellen
mkdir -p a/b/c        # Ordnerstruktur
cp src dst             # kopieren
mv alt neu             # verschieben/umbenennen
rm file                # löschen
rm -r dir              # Ordner löschen
rm -rf dir             # erzwingen (GEFÄHRLICH)

Merksatz:
rm -rf denkt nicht – du musst denken.

5. Dateien anzeigen & bearbeiten
cat file              # komplett anzeigen
less file             # seitenweise (q = exit)
head file              # Anfang
tail file              # Ende
tail -f logfile        # live verfolgen
nano file              # Editor
vim file               # Editor (fortgeschritten)

Merksatz:
less ist mehr als cat.

6. Suchen & Finden
find /pfad -name "*.md"
grep wort file
grep -R wort /pfad

Merksatz:
find sucht Dateien, grep sucht Inhalte.

7. Pipes & Umleitungen
|     # Pipe (Ausgabe → nächster Befehl)
>     # überschreiben
>>    # anhängen

Beispiele:
ls | grep md
dmesg | less
echo test > file

Merksatz:
Pipe verbindet Befehle wie Rohre.

8. Rechte & Besitzer
ls -l
chmod 644 file
chmod +x script.sh
chown user:gruppe file

r = lesen
w = schreiben
x = ausführen

Merksatz:
Ohne x läuft nichts.

9. Benutzer & sudo
whoami
id
su
sudo befehl

- sudo = temporäre Root-Rechte
- niemals dauerhaft als root arbeiten

Merksatz:
sudo gibt Macht – mit Verantwortung.

10. Prozesse & System
ps aux
top / htop
kill PID
uptime
free -h
df -h
du -sh *

Merksatz:
Prozesse fressen Ressourcen – beobachte sie.

11. Paketmanagement (Grundlage)
pacman -S paket
pacman -R paket
apt install paket
dnf install paket

Merksatz:
Paketmanager hält dein System sauber.

12. Hilfe & Lernen
man befehl
befehl --help
apropos wort
history

Merksatz:
man weiß mehr als Google.

13. Wichtige Admin-Gewohnheiten
- Befehle lesen vor Enter
- rm -rf doppelt prüfen
- Logs prüfen (/var/log)
- Befehle verstehen, nicht auswendig lernen

Merksatz:
Ein guter Admin tippt langsam und denkt schnell.
