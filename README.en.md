# ⚖️ Metal Density Calculator

**Aluminium or zinc? The scale tells you for sure.**

🇩🇪 [Deutsch](README.md) · 🇫🇷 [Français](README.fr.md) · 🇬🇧 English · 🇪🇸 [Español](README.es.md)

Looks, weight and sound are misleading: grey, matt aluminium and zinc are constantly mixed up. **Density** is a fixed material property and can be measured with a kitchen scale and a glass of water. This project provides the calculator for it.

![Method](https://img.shields.io/badge/Method-Archimedes'%20principle-2563eb)
![Time](https://img.shields.io/badge/Time-5%20minutes-16a34a)
![Non-destructive](https://img.shields.io/badge/Sample-non--destructive-orange)

---

## 💡 Why density?

| Metal | Density (g/cm³) | Alloy range |
|---|---|---|
| Aluminium | 2.70 | 2.60 – 2.85 |
| Zinc | 7.14 | 6.60 – 7.14 |

Zinc is **almost 2.6 times denser** than aluminium. The ranges do not overlap, so the distinction is reliable. Magnet, sound or colour are only hints.

## 🔬 Principle

A sample immersed in water displaces its own volume of water. With the container on a scale, the scale shows exactly the **mass of the displaced water**. From that you get the volume, then the density.

```
Density = m / Δm × ρ_water
```

| Symbol | Meaning |
|---|---|
| `m` | Dry mass of the sample (g) |
| `Δm` | Scale reading while the sample hangs freely in the water (g) |
| `ρ_water` | Water density, about 0.998 g/cm³ at 20 °C |

## 🧰 What you need

- Digital scale (0.1 g resolution is enough for samples from about 50 g)
- Container (glass or measuring jug, 250–500 ml), half filled with water
- Thin thread and a rod or stand to hold it
- A drop of dish soap (against air bubbles)

## 📋 Procedure

1. **Weigh the sample dry** → note `m`.
2. Put the **water container** on the scale and **tare** it (0.0 g).
3. Tie the sample to the thread and **immerse it fully, hanging freely**. It must touch neither bottom nor wall. Hold the thread by hand or on a stand.
4. **Wipe off air bubbles**, wait until the reading is stable → note `Δm`.
5. Enter the values in the calculator. Done.

> ⚠️ If the sample rests on the bottom, the scale shows the full mass `m`. The measurement is then useless.

## 🖥️ The calculator

Inputs: dry mass `m`, scale reading `Δm`, water temperature (water density is corrected automatically), scale resolution (for the uncertainty) and safety factor `k` (1, 2 or 3).

Outputs: density with uncertainty, sample volume, matching materials from the table, and a scale showing the result among the known metals.

The calculator (`dichterechner.html`) runs fully offline in the browser and is available in **German, French, English and Spanish** (switch at the top right).

## 📱 Install as a phone app

The folder `app/` (or `dichterechner-app.zip`) contains an installable, offline-capable web app (PWA).

1. Put the files on any HTTPS web host, e.g. **GitHub Pages**, **Netlify Drop** or **Cloudflare Pages** (drag the folder in, you get a link).
2. Open the link on your phone.
3. **Android (Chrome):** menu ⋮ → *Install app* / *Add to Home screen*.
4. **iPhone (Safari):** Share button → *Add to Home Screen*.

After the first load the app works without internet.

## 🔥 For anyone melting their own alloys

The method is especially useful for **casting and alloying**: check on the cast piece whether the mix matches the target. Example **Nordic Gold** (used for the 10, 20 and 50 cent euro coins):

| Component | Mass fraction | Density (g/cm³) |
|---|---|---|
| Copper | 89 % | 8.96 |
| Aluminium | 5 % | 2.70 |
| Zinc | 5 % | 7.14 |
| Tin | 1 % | 7.29 |

**Rule of mixtures:** the density of an alloy follows from the mass fractions `w`:

```
1 / ρ_alloy = Σ ( w_i / ρ_i )
```

For Nordic Gold: `0.89/8.96 + 0.05/2.70 + 0.05/7.14 + 0.01/7.29 ≈ 0.1262` → **ρ ≈ 7.9 g/cm³**.

Compare this target with the measurement of your casting:

- **Clearly lower**: porosity, shrinkage cavities, gas inclusions, or too much aluminium.
- **Clearly higher**: too much copper, zinc or tin.
- **Close to target**: mix and casting are probably good.

> ℹ️ With four components, density only gives an **indication**, not the exact composition. Different mixes can give the same density. It is still an excellent test for gross errors and casting defects. Nordic Gold (≈ 7.9) is close to steel in density, but it is non-magnetic and gold-coloured.

> 🦺 **Safety:** never put wet or cold parts into molten metal (splashing). Wear goggles, gloves and protective clothing, and ventilate well. Zinc fumes in particular are harmful. Measure density only on **cooled**, dry pieces.

## 📊 Example

Sample of 100.0 g, water at 20 °C, scale 0.1 g:

| Reading Δm | Density | Result |
|---|---|---|
| 37.0 g | 2.70 g/cm³ | **Aluminium** |
| 14.0 g | 7.13 g/cm³ | **Zinc** |

Rough decision threshold: **4.9 g/cm³**. Below it, aluminium (or magnesium/titanium); above it, zinc, steel or heavier metals.

## ⚠️ Sources of error

- **Air bubbles** reduce `Δm` and raise the calculated density.
- A **thick thread** distorts the volume. Use the thinnest one possible.
- **Small samples** (Δm below about 10 g) are imprecise because the scale resolution weighs more.
- **Cavities and porosity** (castings) lower the measured density.
- **Coatings** (galvanised, anodised, painted) can slightly shift the result on small parts.
- **Floating samples** (density below 1 g/cm³) cannot be measured with this method.

## 📈 Accuracy

The uncertainty is computed from the scale resolution:

```
δρ/ρ ≈ √( (δm/m)² + (δΔm/Δm)² )
```

To tell aluminium from zinc, a simple kitchen scale is plenty: the gap is far larger than the measurement uncertainty.

## 🗂️ Included materials

Magnesium · Aluminium · Titanium · Zinc · Tin · Steel/Iron · Brass · Nickel · Copper · Lead · Nordic Gold

More metals can be added to the `MAT` list in the source code (names, minimum, maximum in g/cm³).

---

*Built for everyone who wants to know what is really inside their piece of metal.*
