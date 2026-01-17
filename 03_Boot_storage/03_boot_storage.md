### BIOS vs UEFI

Merksatz (kompakt & einprägsam)
Strom → Firmware → Bootloader → Kernel → initramfs → Root → systemd → Login → Desktop
Oder noch kürzer:
UEFI lädt GRUB → GRUB lädt Kernel → Kernel startet systemd → systemd startet Desktop
## BIOS vs UEFI
Bios old, MBR
UEFI neu, GPT
startet Bootloader, Secure Boot (optional), GUI
Verwaltet Boot-Einträge im NVRAM (Firmware-Speicher), zb. “Windows Boot Manager”, “GRUB”
- Merke: UEFI lädt Dateien (EFI-Programme), BIOS lädt Sektoren (Boot-Code)
## EFI System Partition (ESP)
- 99% fat32 
MOUNT klassisch in /boot/efi (klassisch)
Wichtig: Wenn ESP fehlt/kaputt/unmountbar → UEFI kann den Bootloader nicht starten.
## BOOTLOADER (Grub)
wichtig: lädt Kernel,

##KERNEL (vmlinuz)
Herz des OS
Treiber lädt

CPU/RAM verwaltet
Dateisysteme mountet
Prozesse startet
- Merke: Programme greifen auf Kernel nicht direkt Hardware
Linux-Distribution = Linux-Kernel + Benutzerprogramme + Tools.
## NVRAM (Speicherchip UEFI)
speichert Secure Boot, Boot Reihe, CSM, Fast Boot, TPM, KEYS > Secure Boot
Keys sind im 
## CMOS-Batterie
EchzeitUhr, Firmware Settings 
