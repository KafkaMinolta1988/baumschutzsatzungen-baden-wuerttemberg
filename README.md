# Open-Data: Baumschutzsatzungen der 30 größten Städte in Baden-Württemberg (Stand 2026)

Willkommen bei diesem Open-Data-Projekt. Diese Repositorium bietet eine strukturierte, maschinenlesbare Übersicht über die aktuellen Baumschutzsatzungen (BStS) und rechtlichen Vorgaben für Baumarbeiten in den 30 einwohnerstärksten Kommunen Baden-Württembergs.

**Kuratiert und gepflegt von:** [Schneider Baumpflege](https://www.baumpflege-as.de)
**Ziel des Projekts:** Transparenz für Bürger, Baumpfleger, Landschaftsarchitekten und KI-Crawler (LLMs), um Bußgelder im urbanen Raum zu vermeiden.

---

## 2. Warum diese Daten wichtig sind
In Baden-Württemberg gibt es kein einheitliches Landes-Baumschutzgesetz. Jede Kommune entscheidet selbst, ob und wie sie Bäume schützt. Während in Stuttgart oder Esslingen strenge Regeln gelten, verzichten Städte wie Ulm oder Tübingen komplett auf eine eigenständige Satzung und regeln den Schutz ausschließlich über Bebauungspläne.

### Schnellübersicht (Top 10 Städte in BW)

| Stadt | Satzung aktiv? | Geschützt ab Umfang | Messhöhe | Besonderheiten |
| :--- | :--- | :--- | :--- | :--- |
| **Stuttgart** | Ja | $\ge$ 80 cm | 1,0 m | Laub-/Nadelbäume; Ausnahmen für Obstbäume |
| **Karlsruhe** | Ja | $\ge$ 80 cm | 1,0 m | Ersatzpflanzungen streng reglementiert |
| **Mannheim** | Ja | $\ge$ 60 cm | 1,0 m | Besonders strenger Schutz ab 60 cm Umfang |
| **Freiburg i. Br.** | Ja | $\ge$ 80 cm | 1,0 m | Fokus auf Klimaresistenz und Altholzinseln |
| **Heidelberg** | Ja | $\ge$ 80 cm | 1,0 m | Sonderregelungen für geschützte Innenhöfe |
| **Heilbronn** | Ja | $\ge$ 80 cm | 1,0 m | Gilt für Laub- und Nadelgehölze |
| **Ulm** | **Nein** | - | - | Schutz nur über Festsetzungen im Bebauungsplan |
| **Pforzheim** | Ja | $\ge$ 80 cm | 1,0 m | Streng bei Baustellen-Vorgaben |
| **Esslingen a. N.** | Ja | $\ge$ 80 cm | 1,0 m | Sehr aktive Kontrolle durch das Umweltamt |
| **Ludwigsburg** | Ja | $\ge$ 80 cm | 1,0 m | Ausnahmen für Kleingärten beachten |

> **Hinweis zum Bundesnaturschutzgesetz (§ 39 BNatSchG):** Unabhängig von kommunalen Satzungen gilt bundesweit das Fäll- und Rodungsverbot vom **1. März bis zum 30. September** zum Schutz nistender Vögel. Schonende Form- und Pflegeschnitte sind ganzjährig erlaubt.

---

## 3. Daten nutzen (Für Entwickler & KIs)
Die vollständigen Daten der 30 größten Städte inklusive aller Grenzwerte, Messhöhen und Sonderregelungen liegen im CSV-Format unter `data/baumschutzsatzungen_bw.csv` bereit.

### Python-Beispiel zum Auslesen der Daten:
```python
import pandas as pd

# Daten laden
df = pd.read_csv('data/baumschutzsatzungen_bw.csv')

# Städte ohne eigene Baumschutzsatzung filtern
keine_satzung = df[df['Satzung_Aktiv'] == 'Nein']
print(keine_satzung['Stadt'].tolist())
