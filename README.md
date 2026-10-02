# ⚖️ Metall-Dichterechner

**Aluminium oder Zink? Die Waage sagt es dir eindeutig.**

Optik, Gewicht und Gefühl täuschen oft: Aluminium und Zink sehen grau und matt sehr ähnlich aus und werden ständig verwechselt. Die **Dichte** dagegen ist eine feste Materialeigenschaft und lässt sich mit einer Küchenwaage und einem Glas Wasser messen. Dieses Projekt liefert den Rechner dazu.

🇩🇪 Deutsch · 🇫🇷 [Français](README.fr.md) · 🇬🇧 [English](README.en.md) · 🇪🇸 [Español](README.es.md)

![Methode](https://img.shields.io/badge/Methode-Archimedisches%20Prinzip-2563eb)
![Aufwand](https://img.shields.io/badge/Aufwand-5%20Minuten-16a34a)
![Zerstörungsfrei](https://img.shields.io/badge/Probe-zerst%C3%B6rungsfrei-orange)

---

## 💡 Warum Dichte?

| Metall | Dichte (g/cm³) | Bereich Legierungen |
|---|---|---|
| Aluminium | 2,70 | 2,60 – 2,85 |
| Zink | 7,14 | 6,60 – 7,14 |

Zink ist **fast 2,6-mal dichter** als Aluminium. Die Bereiche überlappen nicht, daher ist die Unterscheidung sicher. Magnet, Klang oder Farbe sind dagegen nur Indizien.

## 🔬 So funktioniert es

Eine Probe, die ins Wasser taucht, verdrängt Wasser in Höhe ihres eigenen Volumens. Steht das Wassergefäß auf der Waage, zeigt diese genau die **Masse des verdrängten Wassers** an. Daraus folgt das Volumen und damit die Dichte.

```
Dichte = m / Δm × ρ_Wasser
```

| Symbol | Bedeutung |
|---|---|
| `m` | Masse der trockenen Probe (g) |
| `Δm` | Waagenanzeige, wenn die Probe frei im Wasser hängt (g) |
| `ρ_Wasser` | Wasserdichte, ca. 0,998 g/cm³ bei 20 °C |

## 🧰 Was du brauchst

- Digitale Waage (0,1 g Auflösung reicht für Proben ab ca. 50 g)
- Gefäß (Glas oder Messbecher, 250–500 ml), halb mit Wasser gefüllt
- Dünner Faden und ein Stab oder Stativ zum Halten
- Tropfen Spülmittel (gegen Luftblasen)

## 📋 Messablauf

1. **Probe trocken wiegen** → notiere `m`.
2. **Gefäß mit Wasser** auf die Waage stellen und **tarieren** (0,0 g).
3. Probe an den Faden binden und **frei hängend** komplett eintauchen. Weder Boden noch Wand berühren, Faden in der Hand oder am Stativ halten.
4. **Luftblasen abstreifen**, kurz warten bis die Anzeige stabil ist → notiere `Δm`.
5. Werte in den Rechner eingeben. Fertig.

> ⚠️ Liegt die Probe auf dem Boden, zeigt die Waage die ganze Masse `m` an. Die Messung ist dann unbrauchbar.

## 🖥️ Der Rechner

Eingaben:

- Masse trocken `m`
- Waagenanzeige `Δm`
- Wassertemperatur (die Wasserdichte wird automatisch korrigiert)
- Waagenauflösung (für die Unsicherheit)
- Sicherheitsfaktor `k` (1, 2 oder 3)

Ausgabe:

- Dichte mit Unsicherheit
- Probenvolumen
- Passende Materialien aus der Tabelle
- Skala, die den Messwert zwischen den Metallen zeigt

Datei: `dichterechner.html`. Sie läuft komplett offline im Browser, es ist keine Installation nötig. Verfügbar auf **Deutsch, Französisch, Englisch und Spanisch** (Umschalter oben rechts).

## 📱 Als App aufs Handy

Der Ordner `app/` (bzw. `dichterechner-app.zip`) enthält eine installierbare, offlinefähige Web-App (PWA).

1. Dateien auf einen beliebigen HTTPS-Webspace legen, z. B. **GitHub Pages**, **Netlify Drop** oder **Cloudflare Pages** (Ordner hineinziehen, du bekommst einen Link).
2. Link auf dem Handy öffnen.
3. **Android (Chrome):** Menü ⋮ → *App installieren* / *Zum Startbildschirm hinzufügen*.
4. **iPhone (Safari):** Teilen-Symbol → *Zum Home-Bildschirm*.

Nach dem ersten Laden funktioniert die App ohne Internet.

## 🔥 Für alle, die eigene Legierungen schmelzen

Die Methode ist besonders nützlich beim **Schmelzen und Legieren**: Am gegossenen Stück prüfst du, ob die Mischung dem Ziel entspricht. Beispiel **Nordic Gold** (Nordisches Gold, verwendet für die 10-, 20- und 50-Cent-Euromünzen):

| Komponente | Massenanteil | Dichte (g/cm³) |
|---|---|---|
| Kupfer | 89 % | 8,96 |
| Aluminium | 5 % | 2,70 |
| Zink | 5 % | 7,14 |
| Zinn | 1 % | 7,29 |

**Mischungsregel:** Die Dichte einer Legierung ergibt sich aus den Massenanteilen `w`:

```
1 / ρ_Legierung = Σ ( w_i / ρ_i )
```

Für Nordic Gold: `0,89/8,96 + 0,05/2,70 + 0,05/7,14 + 0,01/7,29 ≈ 0,1262` → **ρ ≈ 7,9 g/cm³**.

Diesen Sollwert vergleichst du mit der Messung an deinem Gussstück:

- **Deutlich niedriger**: Porosität, Lunker, Gaseinschlüsse oder zu viel Aluminium.
- **Deutlich höher**: zu viel Kupfer, Zink oder Zinn.
- **Nahe am Sollwert**: Mischung und Guss sind wahrscheinlich gut.

> ℹ️ Bei vier Komponenten liefert die Dichte nur einen **Hinweis**, nicht die genaue Zusammensetzung. Verschiedene Mischungen können dieselbe Dichte ergeben. Für grobe Fehler und Gussfehler ist sie aber ein hervorragender Test. Nordic Gold (≈ 7,9) liegt dichtemäßig nahe bei Stahl, ist aber nicht magnetisch und goldfarben.

> 🦺 **Sicherheit:** Nie feuchte oder kalte Teile in flüssiges Metall tauchen (Spritzgefahr). Schutzbrille, Handschuhe und Schutzkleidung tragen, gut lüften. Besonders Zinkdämpfe sind gesundheitsschädlich. Dichte nur an **abgekühlten**, trockenen Stücken messen.

## 📊 Beispiel

Probe mit 100,0 g, Wasser 20 °C, Waage 0,1 g:

| Anzeige Δm | Dichte | Ergebnis |
|---|---|---|
| 37,0 g | 2,70 g/cm³ | **Aluminium** |
| 14,0 g | 7,13 g/cm³ | **Zink** |

Als Entscheidungsgrenze dient grob **4,9 g/cm³**: Darunter ist es Aluminium (oder Magnesium/Titan), darüber Zink, Stahl oder schwerere Metalle.

## ⚠️ Fehlerquellen

- **Luftblasen** an der Probe machen `Δm` zu klein und die Dichte zu hoch.
- **Dicker Faden** verfälscht das Volumen. Nimm einen möglichst dünnen.
- **Kleine Proben** (Δm unter ca. 10 g) werden ungenau, weil die Waagenauflösung stärker ins Gewicht fällt.
- **Hohlräume und Porosität** (z. B. Guss) senken die gemessene Dichte.
- **Beschichtungen** (verzinkt, eloxiert, lackiert) können bei kleinen Teilen das Ergebnis leicht verschieben.
- **Schwimmende Proben** (Dichte unter 1 g/cm³) sind mit dieser Methode nicht messbar.

## 📈 Genauigkeit

Die Unsicherheit wird aus der Waagenauflösung berechnet:

```
δρ/ρ ≈ √( (δm/m)² + (δΔm/Δm)² )
```

Für Aluminium gegen Zink reicht schon eine einfache Küchenwaage völlig aus, der Unterschied ist viel größer als die Messunsicherheit.

## 🗂️ Enthaltene Materialien

Magnesium · Aluminium · Titan · Zink · Zinn · Stahl/Eisen · Messing · Nickel · Kupfer · Blei · Nordic Gold

Weitere Metalle lassen sich in der Liste `MAT` im Quelltext ergänzen (Name, Minimum, Maximum in g/cm³).

---

*Gebaut für alle, die wissen wollen, was wirklich in ihrem Metallteil steckt.*
