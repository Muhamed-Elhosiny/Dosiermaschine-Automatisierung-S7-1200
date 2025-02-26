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



