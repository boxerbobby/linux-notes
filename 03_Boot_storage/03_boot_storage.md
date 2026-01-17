# Linux Bootprozess – von Power-On bis Desktop

## Merksatz (kompakt & einprägsam)
Strom → Firmware → Bootloader → Kernel → initramfs → Root → systemd → Login → Desktop  
UEFI → GRUB → Kernel → systemd → Desktop

## 1. Einschalten (Power-On)
- Strom an → CPU startet im Reset-Zustand  
- Kontrolle geht an die Firmware des Mainboards

## 2. Firmware (BIOS / UEFI)
# BIOS (alt)
- Initialisiert Hardware  
- Lädt Bootcode aus dem MBR
### UEFI (modern)
- Initialisiert Hardware
- Liest die GPT-Partitionstabelle  
- findet/lädt EFI-Programme (.efi-Dateien)  
- Verwaltet Boot-Einträge im NVRAM (z. B. „Windows Boot Manager“, „GRUB“)  
- Secure Boot optional  
- GPT wird von UEFI gelesen, nicht vom Kernel genutzt, um ESP zu finden
Merke: UEFI lädt Dateien, BIOS lädt Sektoren (Boot-Code)

## 3. EFI System Partition (ESP)
- FAT32-Partition (ca. 100–512 MB)  
- Meist gemountet unter `/boot/efi`  
- Enthält Bootloader-Dateien (z. B. `grubx64.efi`)  
Wichtig: Fehlt oder ist die ESP defekt → Bootloader kann nicht gestartet werden

## 4. Bootloader (GRUB)
- Zeigt optionales Bootmenü  
- Wählt/Lädt Kernel (`vmlinuz`) und `initramfs`  
- Übergibt Kontrolle an den Kernel

## 5. Linux-Kernel (vmlinuz)
- Wird beim Booten in den RAM geladen und entpackt (läuft dauerhaft im RAM)
- Initialisiert CPU, RAM und grundlegende Treiber
- Mountet `initramfs` als temporäres Root-Dateisystem
- Verwaltet CPU & Speicher
- Kontrolliert Hardware über Treiber
- Startet und verwaltet Prozesse
- Ermöglicht das Mounten von Dateisystemen
Merke: Programme greifen nie direkt auf Hardware zu → immer über den Kernel.
Linux-Distribution = Kernel + Benutzerprogramme + Tools

## 6. initramfs
- Temporäres Mini-Linux im RAM  
- Enthält Treiber & Tools (LVM, RAID, LUKS)  
- Findet und mountet das echte Root-Dateisystem (`/`)
- liefert dem Kernel die notwendigen Werkzeuge und Treiber, um System zu finden und zu starten

## 7. Root-Dateisystem (/)
- Echtes Linux-Dateisystem wird aktiv  
- Wichtige Verzeichnisse: `/etc`, `/usr`, `/var`, `/home`

## 8. init-System (systemd)
- Erster Prozess (PID 1)  
- Startet Dienste, Mountpoints (`/etc/fstab`), Netzwerk, Hardware-Services  
- systemd startet und verwaltet das gesamte Linux-System
Merke: Kernel = Motor / systemd = Fahrer

## 9. Display-Manager
- Grafischer Login  
- Startet Benutzer-Session  
- Beispiele: GDM, SDDM, LightDM

## 10. Desktop
- Desktop-Umgebung startet (GNOME, KDE, XFCE)  
- Läuft im Userspace  
- System ist betriebsbereit

##### SONSTIGES
## NVRAM (UEFI-Speicher)
- Speichert Boot-Reihenfolge, Secure Boot, TPM, Keys, Fast Boot, CSM

## Firmware
Firmware ist die erste Software, die Hardware initialisiert und Linux den Start ermöglicht  
Der Chip ist Hardware – das darauf laufende Programm ist Firmware

## CMOS-Batterie
- Versorgt Echtzeituhr  
- Erhält Firmware-Einstellungen ohne Strom
