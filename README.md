# Analyse der Leistung von zwei Photovoltaikanlagen

## Projektziel

In diesem Python-Abschlussprojekt werden Produktions- und Wetterdaten von zwei Photovoltaikanlagen analysiert.

Ziel ist es herauszufinden, wie Sonneneinstrahlung und Temperatur die Stromproduktion beeinflussen. Außerdem wird untersucht, ob einzelne Wechselrichter oder bestimmte Zeiträume ungewöhnlich niedrige Leistungen aufweisen.

## Hauptfrage

Wie beeinflussen Sonneneinstrahlung und Temperatur die Stromproduktion der beiden PV-Anlagen, und lassen sich auffällige Leistungseinbußen erkennen?

## Hypothesen

1. Je höher die Sonneneinstrahlung ist, desto höher ist die erzeugte AC-Leistung.
2. Die Modultemperatur hängt stärker mit der Stromproduktion zusammen als die Außentemperatur.
3. Einzelne Wechselrichter erzeugen weniger Energie als die übrigen Wechselrichter derselben Anlage.
4. Anlage 2 weist häufiger auffällige Leistungseinbrüche auf als Anlage 1.
5. Die höchste Stromproduktion wird ungefähr zur Mittagszeit erreicht.

## Datensatz

Der Datensatz enthält Produktions- und Wetterdaten von zwei Photovoltaikanlagen.

Die Messungen wurden ungefähr alle 15 Minuten durchgeführt und umfassen den Zeitraum vom 15.05.2020 bis zum 17.06.2020.

### Produktionsdaten

Die Produktionsdaten enthalten unter anderem:

- Datum und Uhrzeit
- Anlagen-ID
- Wechselrichter-ID
- DC-Leistung
- AC-Leistung
- Tagesertrag
- Gesamtertrag

### Wetterdaten

Die Wetterdaten enthalten:

- Datum und Uhrzeit
- Anlagen-ID
- Sensor-ID
- Außentemperatur
- Modultemperatur
- Sonneneinstrahlung

## Datenaufbereitung

Vor der Analyse wurden folgende Schritte durchgeführt:

- vier CSV-Dateien eingelesen
- Spalten auf Deutsch umbenannt
- Datumsspalten in ein einheitliches Datumsformat umgewandelt
- fehlende Werte und Duplikate kontrolliert
- Produktionsdaten beider Anlagen zusammengeführt
- Wetterdaten beider Anlagen zusammengeführt
- Produktions- und Wetterdaten über Anlage und Zeitpunkt verbunden
- vier Zeilen ohne passende Wetterdaten entfernt
- zusätzliche Spalten für Tag, Stunde und Wochentag erstellt
- Produktionswerte je Anlage und Messzeitpunkt zusammengefasst
- relative Leistungs- und Einstrahlungswerte berechnet

## Wichtigste Ergebnisse

### Sonneneinstrahlung und AC-Leistung

Bei beiden Anlagen besteht ein sehr starker positiver Zusammenhang zwischen Sonneneinstrahlung und AC-Leistung.

- Anlage 1: Korrelation rund 1,00
- Anlage 2: Korrelation rund 0,91

### Temperatur und AC-Leistung

Die Modultemperatur hängt bei beiden Anlagen stärker mit der AC-Leistung zusammen als die Außentemperatur.

- Anlage 1: Modultemperatur 0,96; Außentemperatur 0,73
- Anlage 2: Modultemperatur 0,87; Außentemperatur 0,65

### Wechselrichter

Bei Anlage 1 liegen die auffälligsten Wechselrichter 9,15 % und 7,70 % unter dem Anlagendurchschnitt.

Bei Anlage 2 liegen die drei schwächsten Wechselrichter 23,52 %, 21,76 % und 19,01 % unter dem Durchschnitt.

### Leistungseinbrüche

Bei Anlage 1 wurde bei hoher Sonneneinstrahlung kein auffälliger Leistungseinbruch erkannt.

Bei Anlage 2 wurden 30 auffällige Messzeitpunkte festgestellt. Das entspricht 5,78 % der untersuchten Messungen mit hoher Sonneneinstrahlung.

Besonders auffällig war der 20.05.2020. Zwischen 10:00 und 14:00 Uhr blieb die AC-Leistung trotz hoher Sonneneinstrahlung deutlich reduziert.

### Tagesverlauf

Beide Anlagen erreichen ihre höchste durchschnittliche AC-Leistung ungefähr zur Mittagszeit.

- Anlage 1: höchste durchschnittliche Leistung um 11 Uhr
- Anlage 2: höchste durchschnittliche Leistung um 12 Uhr

## Fazit

Die Sonneneinstrahlung ist der wichtigste untersuchte Einflussfaktor auf die Stromproduktion.

Anlage 1 zeigt insgesamt einen gleichmäßigeren Zusammenhang zwischen Sonneneinstrahlung und Leistung. Anlage 2 weist größere Unterschiede zwischen den Wechselrichtern und mehrere auffällige Leistungseinbrüche auf.

Die auffälligen Wechselrichter und Zeiträume von Anlage 2 sollten technisch genauer untersucht werden. Die genaue Ursache der Abweichungen kann mit den vorhandenen Daten jedoch nicht bestimmt werden.

## Einschränkungen

- Der Datensatz umfasst nur ungefähr 34 Tage.
- Standort und installierte Leistung der Anlagen sind nicht bekannt.
- Informationen zu Wartungen, Störungen und Abschaltungen fehlen.
- Die absoluten Leistungswerte der Anlagen sind nicht direkt vergleichbar.
- Korrelationen zeigen Zusammenhänge, aber keine eindeutigen Ursachen.
- Die Grenzen zur Erkennung eines Leistungseinbruchs wurden für diese Analyse selbst festgelegt.

## Verwendete Technologien

- Python
- Pandas
- Plotly Express
- Jupyter Notebook
- Visual Studio Code

## Projektdateien

- `main.ipynb` – vollständige Datenbereinigung und Analyse
- `Plant_1_Generation_Data.csv` – Produktionsdaten von Anlage 1
- `Plant_1_Weather_Sensor_Data.csv` – Wetterdaten von Anlage 1
- `Plant_2_Generation_Data.csv` – Produktionsdaten von Anlage 2
- `Plant_2_Weather_Sensor_Data.csv` – Wetterdaten von Anlage 2
- `pv_analyse_bereinigt.csv` – vollständige bereinigte Analysetabelle
- `pv_zeitpunkte.csv` – zusammengefasste Messwerte pro Anlage und Zeitpunkt
- `wechselrichter_ergebnisse.csv` – Erträge und Abweichungen der Wechselrichter
- `auffaellige_leistungseinbrueche.csv` – erkannte auffällige Messzeitpunkte


## Datenquelle

Die verwendeten Ausgangsdaten stammen aus dem öffentlich verfügbaren Kaggle-Datensatz:

[Solar Power Generation Data](https://www.kaggle.com/datasets/anikannal/solar-power-generation-data)

Der Datensatz enthält Produktions- und Sensordaten von zwei Photovoltaikanlagen.
