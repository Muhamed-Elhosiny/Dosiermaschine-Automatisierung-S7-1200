# Dosiermaschine-Automatisierung-S7-1200

 ## 📌 Einführung  
**Dieses Projekt ist eine Automatisierungslösung für eine Dosiermaschine unter Verwendung einer Siemens S7-1200 SPS.**  
Es umfasst die **SPS-Programmierung**, die **Motorsteuerung** und die **Sensorintegration**, um den Dosier- und Mischprozess zu automatisieren.  

![image](https://github.com/user-attachments/assets/0304a67b-8fdc-4382-94d6-65f1d51ec326)

## 📌 Dosiermaschinen-Komponenten


### ⚙️ Motoren:  
1. **Zuführungsaufzug 1:** Direktantrieb **3 kW**  
2. **Zuführungsaufzug 2:** Direktantrieb **3 kW**  
3. **Spiralförderer 1:** Frequenzumrichter (VFD) **1 kW**  
4. **Spiralförderer 2:** Frequenzumrichter (VFD) **1 kW**  
5. **Mischer:** Frequenzumrichter (VFD) **5,5 kW**  

### 🎯 Analoge Sensoren:  
- **Dosiersilo 1 Wägezelle:** 4-20 mA  
- **Dosiersilo 2 Wägezelle:** 4-20 mA  

### 🔧 Digitale Aktuatoren:  
- **Mischer-Schlauchventil:** 24VDC

## Motorenbewertungen, Schutz und Verkabelung

### Aufzug 1, 2
- **Leistung:** 3 kW
- **Spannung:** 380 V AC, 3-Phasen
- **Schütz:** AC-3
- **Strom:** (I = W / (V × 0.7 × 1.73)) = 6,5 A
- **Überlastschutz:** Mindestens 6,5 A
- **Entfernung:** 5 m
- **Kabel:** 1 × 1,5 mm²

### Mischer
- **Leistung:** 5,5 kW
- **Spannung:** 380 V AC, 3-Phasen
- **Geschwindigkeitsregelung:** Erforderlich (VFD 5,5 kW)
- **Strom:** (I = W / (V × 0.7 × 1.73)) = 12 A
- **Überlastschutz:** Nicht erforderlich
- **Entfernung:** 5 m
- **Kabel:** 1 × 2,5 mm²

### Spirale 1, 2
- **Leistung:** 1 kW
- **Spannung:** 380 V AC, 3-Phasen
- **Geschwindigkeitsregelung:** Erforderlich (VFD 1 kW)
- **Strom:** (I = W / (V × 0.7 × 1.73)) = 2,2 A
- **Überlastschutz:** Nicht erforderlich
- **Entfernung:** 5 m
- **Kabel:** 1 × 1,5 mm²

### Gesamtleistungsaufnahme
- 3 kW × 2 + 5,5 kW + 1,1 kW × 2 = 13,7 kW

### Kabelverlängerungen vom Motor zu den elektrischen Schalttafelklemmen
- **3 Phasen × 20 Meter** = **60 m von 1 × 1,5 mm²**
- **3 Phasen × 5 Meter** = **15 m von 1 × 2,5 mm²**

# Analoge Wägezellen

## Verkabelung der Wägezellen:

### 1. Wägezellen
- Abstand: 1 m
- Kabel: 4x0,75 mm² abgeschirmt

### 2. Analysatoren
- Signal: 4-20 mA
- Abstand: 6 m
- Kabel: 4x0,75 mm² abgeschirmt
---
## Stromverbrauch:

- **20 mA pro PLC-Eingang:** 20 mA × 2 = **40 mA**
- **Interner Verbrauch pro Gerät:** 8 mA × 2 = **16 mA**
- **Gesamtverbrauch:** **56 mA**
---
## Verkabelung vom Sensor zu den Anschlussklemmen:

- **8 Wägezellen** = 8 × 1 m = **8 m**
- **2 Analysatoren** = 2 × 6 m = **12 m**
- **Gesamtlänge der Kabel:** **20 m (4x0,75 mm²)**

# Aktor-Relais und Verkabelung

## Komponenten und Verkabelung:

| Aktor        | Relais-Typ      | Kabeltyp       |
|-------------|---------------|--------------|
| Mixer       | 24VDC Relais  | 1×0,75 mm²  |
| Spirale 1   | 24VDC Relais  | 1×0,75 mm²  |
| Spirale 2   | 24VDC Relais  | 1×0,75 mm²  |
| Aufzug 1    | 24VDC Relais  | 1×0,75 mm²  |
| Aufzug 2    | 24VDC Relais  | 1×0,75 mm²  |
| Mixer-Tor   | 24VDC Relais  | 1×0,75 mm²  |
---
## Gesamter Stromverbrauch:

- **Durchschnittlicher Verbrauch pro PLC-Ausgang:** 12 mA
- **Verbrauch pro Relais-Spule:** 9 mA
- **Berechnung:**
  - **PLC-Ausgänge:** 12 mA × 6 = **72 mA**
  - **Relais-Spulen:** 9 mA × 6 = **54 mA**
  - **Gesamtstromverbrauch:** **135 mA**
---
### Hinweis:
Jeder PLC-Ausgang verbraucht im Durchschnitt **12 mA**, und jede Relais-Spule benötigt **9 mA**.



