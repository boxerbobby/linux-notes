## Das Linux-Dateisystem
### alles ist eine Datei, Drucker, Docs, Programme, Prozesse, Festplatte wie /dev/sda, usb-stick

/bin - ls, cp, mv oder cat - grundlegende Systemprogramme
/sbin - fdisk, ifconfig, Systemprogramme für administrative Aufgaben (oft root)
/etc - Konfigurationverzeichnis, Textdateien, die das Verhalten von Programmen und Diensten steuern. Die Netzwerkkonfiguration, Benutzerkonten (/etc/passwd), Gruppeninformationen und Dienstkonfigurationen 
/home - persönliches verzeichniss vom Benutzer, Docs, Bilder, Einstellungen
/root - Heimatverzeichnis Root, außerhalb /home damit der Administrator auch Zugriff hat, wenn /home auf einer separaten Partition liegt, die nicht gemountet werden konnte.
/var - "variable", Daten die sich während Betrieb ändern
/tmp - Inhalt oft bei reboot gelöscht
/opt - optional installierte Software, gedacht für nicht aus Paketquellen 
/proc - virtuelles Datensystem, existiert im speicher(nicht Festplatte), /proc zeigt Live-Informationen über das System. Inhalte ändern sich dynamisch, je nach Systemzustand. Jeder laufende Prozess hat ein eigenes Verzeichnis. (Prozess-ID PID)
/sys - virtuelles Datensystem -> Kernel, Objekte, Treiber, Hardware, Treiber
/mnt /media - Einhängepunkte (Mountpoints) für Dateisysteme. /Media Wechselmedien wie USB-Sticks gemountet, /mnt traditionell manuelles temp mount 
/usr - ("Unix System Resources")
/lib /lib64 - Bibliotheken (vergleichbar mit DLL-Dateien unter Windows), die von Programmen in /bin und /sbin benötigt werden
/boot - alles für boot - Kernel, initramfs, Bootloader
/dev - Gerätedateien. Hier erscheinen Festplatten als /dev/sda, /dev/sdb, Partitionen als /dev/sda1, Terminals als /dev/tty

## Dateisystemtypen
ext4
XFS
Btrfs - "B-tree File System", Schutz vor Datenverlust bei Abstürzen, Grundlage für Snapshots 
ZFS - extreme Datenintegrität und wird oft für Speicherserver eingesetzt
