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

# SPS-Auswahl

## Digitale Ausgänge:
1. Mixer  
2. Spirale 1  
3. Spirale 2  
4. Aufzug 1  
5. Aufzug 2  
6. Mixer-Tor  
7. Reserve 1  
8. Reserve 2  
---
## Digitale Eingänge:
1. Mixer VFD Überlast (OVLD)  
2. Spirale 1 VFD Überlast (OVLD)  
3. Spirale 2 VFD Überlast (OVLD)  
4. Aufzug 1 Überlast (OVLD)  
5. Aufzug 2 Überlast (OVLD)  
6. Not-Aus (EMGC Stop)  
7. Reserve 1  
8. Reserve 2  
---
## Analoge Ausgänge:
1. VFD1 Frequenz  
2. VFD2 Frequenz  
---
## Analoge Eingänge:
1. Wägezellen-Analysator 1  
2. Wägezellen-Analysator 2

 # DC-Leistungsaufnahme und Stromversorgung

## Stromverbrauch:
- **Digitale Ausgänge:** 12 mA × 8 = **96 mA**
- **Digitale Eingänge:** 12 mA × 8 = **96 mA**
- **Analoge Eingänge:** 20 mA × 2 = **40 mA**
- **Analoge Ausgänge:** 12 mA × 2 = **72 mA**
- **Relais:** 9 mA × 8 = **72 mA**
- **PLC intern:** **20 mA**
- **VFD intern:** 5 mA × 3 = **15 mA**
- **Analysator:** 8 mA × 2 = **16 mA**
- **Gesamtverbrauch:** **427 mA**

## Stromversorgung:
Eine **24VDC 1A Industrie-Stromversorgung** mit **Kurzschlussschutz** ist mehr als ausreichend.

# Hauptleistungsschalter

## Gesamtstromberechnung:
**Gesamtstrom = 13,7 kW / (380 × 0,7 × 1,73) = 30A**

**Hinweis:** Ein Hauptleistungsschalter wird hauptsächlich verwendet, um das **Eingangs-Stromkabel** zu schützen.

## Schritte zur Auswahl des Hauptleistungsschalters:

1. **Kabellänge berechnen**  
   - Notwendige Kabellänge zwischen der Hauptstromquelle (Transformator, Stromverteilung) und dem Hauptleistungsschalter.  
   - In unserem Fall nehmen wir **10 m** an.

2. **Gesamtstromverbrauch des Schaltkastens berechnen**  
   - Fallannahme: **30A × 10 (für Einschaltströme) = 300A**

3. **Geeignete Kabellösung testen**  
   - 2,5 mm² Kabel mit einem Widerstand von **0,00831 Ω pro Meter**.  
   - Ist der Spannungsabfall **unter 3%**?

4. **Spannungsabfall berechnen:**  
   **Spannungsabfall (%) = (1,73 × Strom × Kabelimpedanz pro Meter × Kabellänge × 100) / Spannungsquelle**  
   **Berechnung:**  
   **(1,73 × 30 × 0,00831 × 10 × 100) / 380 = 1,11%**  
   - **Weniger als 3%, akzeptabel!**

5. **Maximaler Strom für 2,5 mm² Kabel prüfen**  
   - Laut Tabelle: **32A**  
   - **Daher sollte der Hauptschutzschalter mit 32A, Typ C, ausgelegt sein.**

# Leitungsschutzschalter (MCBs)

1. **24VDC Stromversorgung:**  
   - **MCB:** 1A  
   - **Typ:** 1-poliger MCB  
   - **Funktion:** Schalten  

2. **PLC Steuerstromkreis:**  
   - **MCB:** 1A  
   - **Typ:** 1-poliger MCB  
   - **Funktion:** Schalten  

## Algorithm

![image](https://github.com/user-attachments/assets/0d13ced7-8079-4726-b3e4-c6acd0789838)

## 📂 Dosierungsmaschine_TIA_Portal
 ┣ 📂 PLC_Tags                 # (PLC-Variablentabelle)
 ┣ 📂 Hauptprogramm            # (Main_Program)
 ┣ 📂 Funktionsbausteine       # (Function_Blocks)
 ┃ ┣ 📜 FSM_Controller.fb      # (Finite-State-Machine-Funktionsbaustein)
 ┃ ┣ 📜 DosingBlock.fb         # (Dosierblock-Funktionsbaustein)
 ┃ ┗ 📜 Timer.fb               # (Timer-Funktionsbaustein)


# 📌 TIA-Portal PLC-Tag-Tabelle für die Dosierungsmaschine

![image](https://github.com/user-attachments/assets/985a74a1-2446-4f8c-b2c9-8d9fe72f8b43)

![image](https://github.com/user-attachments/assets/e56aed77-5b5d-46e2-81a9-8a813ff4907f)

## Programm: Ladder Diagram for Dosierungsmaschine_Main  

## Netzwerk 1: FSM-Controller-Funktionsblock

![image](https://github.com/user-attachments/assets/034a56bd-bdfc-4e38-831b-4049bcd5c51f)

## Netzwerk 2: Aufruf des Dosierblock-Funktionsblocks

![image](https://github.com/user-attachments/assets/1482e683-a8a0-49d7-81b3-3b73542faf95)

## Netzwerk 3: Aufruf von Silo 1 und 2

![image](https://github.com/user-attachments/assets/de1ce060-a134-4c8e-bc67-645c020e2119)

![image](https://github.com/user-attachments/assets/ae3fbb08-ff66-4fe7-bea5-beac3e505417)

## Netzwerk 4: Aktivierung des Timer-Blocks

![image](https://github.com/user-attachments/assets/0965489c-093f-4534-b569-2da973f4c467)

## Network 5: Not-Aus Schalter

![image](https://github.com/user-attachments/assets/e4961629-20ae-41bb-95d0-320dd29455a3)


# FSM-Controller-Funktionsblock

![image](https://github.com/user-attachments/assets/1754eea5-10a7-45dd-98cb-eaa4ba1607d3)

![image](https://github.com/user-attachments/assets/696045f0-68af-40ee-9357-76b53d16dcc6)

![image](https://github.com/user-attachments/assets/167ada2d-fb1c-4720-9fd0-8c347d000e1b)

![image](https://github.com/user-attachments/assets/9440e067-7a1e-494f-bfa3-317cfa3eeecd)

# Dosierblock_FB [FB1]

![image](https://github.com/user-attachments/assets/99bfe8a6-5fb8-4223-83d4-cd29aad5cb58)

![image](https://github.com/user-attachments/assets/3647a605-c640-4f9a-98d4-90c1471cc792)

![image](https://github.com/user-attachments/assets/e535c5aa-0d86-4982-8c05-02e96482ceda)

# Zeitsteuerung [FB4]

![image](https://github.com/user-attachments/assets/43b8c39d-d220-426a-8ffe-047a455ecb4e)









 










