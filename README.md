# 📊 Statistik Projekt – Techno GmbH Analyse
### Statistik Abschlussprojekt | Dozent: V. Joswig | KW07 2026

![R](https://img.shields.io/badge/R-276DC3?style=for-the-badge&logo=r&logoColor=white)
![Statistics](https://img.shields.io/badge/Statistik-Inferenzstatistik-blueviolet?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Abgeschlossen-brightgreen?style=for-the-badge)

---

## 📋 Projektbeschreibung

Dieses Projekt analysiert vier statistische Fragestellungen der **Techno GmbH**, die sich in schwierigen Zeiten zukunftsorientiert aufstellen möchte. Für jede Fragestellung wurden geeignete Testverfahren ausgewählt, Voraussetzungen geprüft und statistisch fundierte Handlungsempfehlungen erarbeitet.

**Rahmenbedingungen:**
- Signifikanzniveau: α = 0,05
- Teststärke (Power): 1 − β = 0,90
- Werkzeug: R / R-Commander (Rcmdr)
- Berichtssprache: Deutsch

---

## 🔬 Projektaufgaben & Ergebnisse

---

### 1️⃣ Lieferantenbeurteilung

**Fragestellung:** Unterscheidet sich die Produktzuverlässigkeit der Lieferanten signifikant? Gibt es einen Zusammenhang zwischen Produktkategorie und Zuverlässigkeit?

**Methode:** Chi Quadrat Unabhängigkeitstest (n = 559)

| Fragestellung | p-Wert | Entscheidung |
|---|---|---|
| a) Unterschied zwischen Lieferanten | < 0,001 | H0 **abgelehnt** – hochsignifikanter Unterschied |
| b) Zusammenhang Produktkategorie | 0,1774 | H0 **beibehalten** – kein signifikanter Zusammenhang |

**Handlungsempfehlung:**
- **Lieferant A** priorisieren (50% hochzuverlässig, nur 18,8% niedrig)
- **Lieferant C** kritisch prüfen (fast 40% niedrige Zuverlässigkeit → Kandidat für Beendigung)
- **Lieferant B** durch Qualitätsaudits auf Niveau von A heben

---

### 2️⃣ Energieverbrauch

**Fragestellung:** Führt die Veränderung der Produktionsmittel zu einer signifikanten Absenkung des Energieverbrauchs?

**Methode:** Einseitiger t-Test für unabhängige Stichproben (n = 50 pro Gruppe)

| Parameter | Herkömmlich | Neuartig |
|---|---|---|
| Mittelwert | 347,44 kWh | 313,55 kWh |
| Differenz | — | **−33,89 kWh** |
| p-Wert (einseitig) | — | **0,0009** |
| Cohen's d | — | 0,6411 (mittelstarker Effekt) |
| Power | — | 0,9381 ✅ |

**Fazit:** H0 abgelehnt. Die Umstellung auf neuartige Produktionsmittel senkt den Energieverbrauch hochsignifikant um durchschnittlich ~34 kWh/Einheit. Vollständige Umstellung empfohlen.

---

### 3️⃣ Standzeit

**Fragestellung:** Welche Variante erzielt die längste Standzeit?

**Methoden:** Gepaarter t-Test (V1 vs. V4) + Welch ANOVA + Tukey Posthoc Test

| Variante | Mittelwert (h) | Bewertung |
|---|---|---|
| V1 – Aktuell | 500,56 | Referenz |
| V2 – Neu 1 | 483,79 | ❌ Schlechteste Performance |
| V3 – Neu 2 | **523,37** | ✅ Numerisch beste Standzeit |
| V4 – Speed | 515,84 | ✅ Statistisch gleichwertig zu V3 |

**Tukey Post-hoc Ergebnisse:**

| Vergleich | p-Wert | Ergebnis |
|---|---|---|
| V3 vs. V4 | 0,581 | Kein signifikanter Unterschied |
| V3 vs. V2 | < 0,001 | V3 deutlich überlegen |
| V4 vs. V2 | < 0,001 | V4 deutlich überlegen |

**Empfehlung:** V3 bei Priorisierung maximaler Standzeit. V4 bei kostengünstigerer Umsetzung, da kein signifikanter Leistungsverlust gegenüber V3.

---

### 4️⃣ Prozessvereinfachung (Klebeprozess)

**Fragestellung:** Welche Faktoren (Dauer, Feuchte, Temperatur) beeinflussen die Klebequalität signifikant?

**Methode:** Mehrfaktorielle ANOVA (Typ II, n = 240)

| Faktor | p-Wert | Signifikanz |
|---|---|---|
| Dauer (D) | 0,6053 | ❌ Nicht signifikant |
| Feuchte (F) | < 2,2e-16 | ✅ Hochsignifikant |
| Temperatur (T) | 0,6999 | ❌ Nicht signifikant |
| Feuchte : Temperatur (WW) | < 0,001 | ✅ Starke Wechselwirkung |

**Optimale Prozessbedingung:** Feuchte = Tief + Temperatur = Tief → ~90 Qualitätspunkte

**Handlungsempfehlung:**
- **Dauer kann gekürzt werden** – kein Qualitätsverlust (p = 0,605) → Durchsatzsteigerung + Kostensenkung
- Fokus der Qualitätskontrolle auf **Feuchtesteuerung** legen
- Temperatur und Feuchte stets **kombiniert** überwachen (signifikante Wechselwirkung)

---

## 📁 Projektstruktur

```
Statistik Projekt/
├── Projekt_Mehmet_Durular.pdf   ← Ausgearbeiteter Projektbericht
├── Daten_KW07.xlsx              ← Rohdaten (4 Datensätze)
└── README.md
```

---

## 🛠️ Verwendete Werkzeuge & Testverfahren

| Verfahren | Einsatzgebiet |
|---|---|
| Chi Quadrat Test | Lieferantenbeurteilung (nominale Daten) |
| t-Test (unabhängig, einseitig) | Energieverbrauch (2 Gruppen) |
| Shapiro WilkTest | Normalverteilungsprüfung |
| Levene Test | Varianzhomogenität |
| Gepaarter t-Test | Standzeit V1 vs. V4 |
| Welch ANOVA | Standzeit V2, V3, V4 (ungleiche Varianzen) |
| Tukey Post hoc | Paarweise Vergleiche nach ANOVA |
| Mehrfaktorielle ANOVA (Typ II) | Prozessvereinfachung (3 Faktoren) |
| G*Power | Effektstärke & Power Analyse |

---

*alfatraining Bildungszentrum GmbH | Modul: Statistik | Stand: KW07 2026*
