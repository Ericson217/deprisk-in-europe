# deprisk-in-europe

## Maschinelles Lernen zur geschlechtsspezifischen Identifikation von Depressionsrisiken

Dieses Repository enthält die Datenanalyse und den Code für die Seminararbeit im Bereich Gesundheitsökonomie. Die Arbeit untersucht die Prädiktoren für klinische Depressionen bei Erwachsenen mittleren und höheren Alters in Europa unter Anwendung eines hybriden Machine-Learning-Ansatzes.

## 📋 Projektübersicht

Depressionen stellen eine erhebliche ökonomische und soziale Belastung für europäische Gesundheitssysteme dar. Ziel dieser Untersuchung ist es, mithilfe von Machine-Learning-Verfahren (ML) komplexe Risikoprofile zu identifizieren, die über klassische statistische Modelle hinausgehen.

**Zentrale Fragestellung:** Welche Risiko- und Schutzfaktoren für Depressionen können mittels maschinellen Lernens bei Männern und Frauen (50+) in Europa identifiziert werden?

**Datenbasis:** easySHARE-Datensatz (Welle 8), umfassend Daten aus über 20 europäischen Ländern.

**Zielvariable:** Klinische Depression, operationalisiert über die EURO-D-Skala (Cut-off ≥ 4).

## 🛠 Methodik

Die Analyse folgt einem zweistufigen empirischen Verfahren, implementiert in R:

### Data Preprocessing & Imputation
* Behandlung fehlender Werte mittels Multiple Imputation by Chained Equations (MICE)
* Generierung von 10 imputierten Datensätzen mit jeweils 35 Iterationen zur Sicherstellung der Konvergenz

### Feature Selection (Random Forest)
* Einsatz einer Random-Forest-Analyse (RFA) zur Identifikation der bedeutsamsten Prädiktoren aus 31 Variablen
* Bestimmung der Variablenwichtigkeit via Permutation Variable Importance (pVI)

### Inferenzstatistik (Logistische Regression)
* Validierung der Top-Prädiktoren in geschlechtsspezifischen logistischen Regressionsmodellen
* Auswahl der Variablen basierend auf dem Diskriminationskoeffizienten nach Tjur (D_Tjur)

## 📈 Hauptergebnisse

Die Modelle erzielten eine durchschnittliche Fehlerrate von 12,14% (Männer) bzw. 17,42% (Frauen). Als stärkste Prädiktoren über beide Geschlechter hinweg stellten sich heraus:

* **Muskelschwäche-Index:** Ein signifikanter körperlicher Risikofaktor (Odds Ratio bis zu 1,70)
* **Neurotizismus:** Bestätigung der psychologischen Disposition als zentraler Einflussfaktor (Odds Ratio bis zu 1,60)
