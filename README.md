# Visualisierungsmöglichkeiten mit Python – Auswertung von Ngspice-Simulationsdaten im Rahmen der gm/Id-Designmethodik

## 📘 Projektbeschreibung
Dieses Projekt untersucht, wie sich **Ngspice-Simulationsdaten** mithilfe von **Python** effizient einlesen, analysieren und visualisieren lassen.  
Als methodischer Rahmen dient die **gm/Id-Designmethodik**, die in der analogen Schaltungsentwicklung eine zentrale Rolle bei der Transistorauslegung spielt.  

Das Ziel besteht darin, verschiedene Python-Bibliotheken auf ihre Eignung zur **Datenanalyse und Visualisierung** zu untersuchen und typische Auswertungen aus der gm/Id-Methodik, wie die Abhängigkeit von **gm/Id** über **Vov (Vgs − Vth)**, darzustellen.

---

## 🧠 Theoretischer Hintergrund

Die **gm/Id-Methodik** (Transkonduktanz-zu-Strom-Verhältnis) ist eine effiziente Entwurfstechnik für analoge CMOS-Schaltungen.  
Sie erlaubt die dimensionslose Darstellung der Transistorbetriebsregionen und liefert eine direkte Beziehung zwischen **Effizienz (gm/Id)** und **Übersteuerungsspannung (Vov)**.

Die Auswertung der gm/Id-Kennlinie ermöglicht u. a.:
- die Bestimmung des optimalen Arbeitspunkts eines Transistors,
- die Ermittlung der Transistorauslegung für ein gegebenes gm-/Id-Verhältnis,
- und die Beurteilung der Energieeffizienz.

---

## 🧩 Datengrundlage

Die Daten stammen aus **Ngspice-Simulationen** und wurden im `.csv`-Format gespeichert.  

test_gmid130.txt
test_gmid500.txt
test_gmid1000.txt
test_gmid_130_500_1000.csv


Beispielhafte Dateien:

