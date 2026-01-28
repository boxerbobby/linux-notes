# Linux Terminal – Grundlagen (Nano-Format)

## 1. Terminal & Shell – Grundverständnis
Terminal = Textoberfläche | Shell = Befehlsinterpreter (meist bash)  
- Terminal ist das Werkzeug | Shell führt Befehle aus | CLI: schneller, skriptfähig, server-tauglich  
Merksatz: Terminal ist das Fenster – die Shell denkt für dich.
## 2. Aufbau eines Befehls
Syntax: befehl [optionen] [argumente]  
Bsp: ls -l /etc | cp -r dir1 dir2  
- Optionen: ändern Verhalten (-l, -a) | Argumente: Ziel oder Quelle  
Merksatz: Befehl sagt WAS, Option sagt WIE, Argument sagt WO.
## 3. Navigation im Dateisystem
pwd        # zeigt aktuelles Verzeichnis  
ls         # listet Inhalte (Dateien/Ordner)  
ls -la     # detailliert + versteckte Dateien (.)  
cd /pfad   # wechselt in /pfad  
cd ..      # eine Ebene hoch  
cd ~       # ins Home-Verzeichnis  
Merksatz: pwd wo bin ich, ls was ist da, cd wohin gehe ich.
## 4. Dateien & Ordner verwalten
touch file.txt        # erstellt leere Datei (oder aktualisiert Zeitstempel)  
mkdir dir             # erstellt Ordner  
mkdir -p a/b/c        # erstellt Ordnerstruktur inkl. Elternordner  
cp src dst            # kopiert Datei/Ordner (Ordner meist mit -r)  
mv alt neu            # verschiebt oder benennt um  
rm file               # löscht Datei  
rm -r dir             # löscht Ordner rekursiv  
rm -rf dir            # erzwingt rekursives Löschen ohne Rückfrage (GEFÄHRLICH)  
Merksatz: rm -rf denkt nicht – du musst denken.
## 5. Dateien anzeigen & bearbeiten
cat file              # zeigt Datei komplett  
less file             # zeigt seitenweise (q = exit)  
head file             # zeigt Anfang (standard: 10 Zeilen)  
tail file             # zeigt Ende (standard: 10 Zeilen)  
tail -f logfile       # folgt Logdatei live (neue Zeilen in Echtzeit)  
nano file             # öffnet Editor nano  
vim file              # öffnet Editor vim (fortgeschritten)  
Merksatz: less ist mehr als cat.
## 6. Suchen & Finden
find /pfad -name "*.md"   # findet Dateien nach Namen im Pfad  
grep wort file            # sucht "wort" in einer Datei  
grep -R wort /pfad        # sucht rekursiv in Dateien unter /pfad  
Merksatz: find sucht Dateien, grep sucht Inhalte.
## 7. Pipes & Umleitungen
|    # Pipe: Ausgabe von A geht als Eingabe an B  
>    # schreibt Ausgabe in Datei (überschreibt)  
>>   # schreibt Ausgabe in Datei (hängt an)  
Bsp: ls | grep md | dmesg | less | echo test > file  
Merksatz: Pipe verbindet Befehle wie Rohre.
## 8. Rechte & Besitzer
ls -l                 # zeigt Rechte, Besitzer, Gruppe  
chmod 644 file        # setzt Rechte (rw-r--r--)  
chmod +x script.sh    # macht Datei ausführbar  
chown user:gruppe file# ändert Besitzer und Gruppe  
r=lesen | w=schreiben | x=ausführen  
Merksatz: Ohne x läuft nichts.
## 9. Benutzer & sudo
whoami      # zeigt aktuellen Benutzer  
id          # zeigt UID/GIDs und Gruppen  
su          # Benutzer wechseln (ohne Name: zu root, falls erlaubt)  
sudo befehl # führt Befehl mit Adminrechten aus (passwortgeschützt)  
- sudo = temporäre Root-Rechte | niemals dauerhaft als root arbeiten
## 10. Prozesse & System
ps aux      # zeigt laufende Prozesse (alle Benutzer)  
top/htop    # Live-Ansicht von Prozessen und Last (htop komfortabler)  
kill PID    # beendet Prozess mit Prozess-ID (Signal, standard: TERM)  
uptime      # zeigt Laufzeit + Systemlast (load)  
free -h     # zeigt RAM/Swap (human readable)  
df -h       # zeigt freien/belegten Plattenplatz je Dateisystem  
du -sh *    # zeigt Größe der Inhalte im aktuellen Ordner (summiert, lesbar)  
Merksatz: Prozesse fressen Ressourcen – beobachte sie.
## 11. Paketmanagement (Grundlage)
pacman -S paket     # installiert Paket (Arch)  
pacman -R paket     # entfernt Paket (Arch)  
apt install paket   # installiert Paket (Debian/Ubuntu)  
dnf install paket   # installiert Paket (Fedora/RHEL)  
Merksatz: Paketmanager hält dein System sauber.
## 12. Hilfe & Lernen
man befehl        # Handbuchseite zum Befehl  
befehl --help     # kurze Hilfe/Optionen  
apropos wort      # sucht Manpages nach Stichwort  
history           # zeigt zuletzt eingegebene Befehle  
Merksatz: man weiß mehr als Google.
## 13. Wichtige Admin-Gewohnheiten
- Befehle lesen vor Enter  
- rm -rf doppelt prüfen  
- Logs prüfen: /var/log  
- Befehle verstehen, nicht auswendig lernen  
Merksatz: Ein guter Admin tippt langsam und denkt schnell.