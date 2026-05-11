# ARC-Devs

ARC-Devs er projektets proces- og udviklingsanker for Skolehaven 4.0 - AI-accelereret.

Formålet er at gøre udviklingsarbejdet løbende synligt: PCB-status, komponentbestillinger, bring-up, testnoter, firmwarestatus, billeder, måledata og milepæle kan samles her eller linkes herfra til de aktive udviklingsrepos.

## Aktuel status

- ARC-Probe PCB-designet bestilt. Printpladerne produceres med ENIG-overfladefinish og forventes afsendt fra Tyskland den 19. maj 2026.
- ST-udviklingsværktøj med STM32WBA5 Bluetooth-modulet er til rådighed, så firmwaretest kan påbegyndes parallelt med PCB-produktionen.
- Komponenter til første ARC-Probe bring-up, bestilt hos Mouser 29. april 2026, er modtaget.
- Når printpladerne modtages, starter ARC-Probe bring-up med montage, strømtest, sensorvalidering, firmwareintegration og første måledata.
  
## Foreslået struktur

- `arc-probe-bringup-log.md` - PCB, komponenter, montage, strøm, sensorer og første data.
- `milestones.md` - kort status på tværs af ARC-Probe, ARC-Light, gateway/app og pilot.
- `images/` - kuraterede billeder fra PCB, montage, test og pilot.
- `data/` - udvalgte måledata fra bring-up og pilot.

## Arbejdsprincip

Udviklingen fortsætter under ansøgningsprocessen. Det betyder, at ansøgningen ikke kun beskriver en plan, men kan kobles til en levende proces med Git-sporbarhed, statusnoter og dokumenteret fremdrift.
