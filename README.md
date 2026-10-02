# ⚖️ Calculateur de densité des métaux

**Aluminium ou zinc ? La balance vous répond sans ambiguïté.**

🇩🇪 [Deutsch](README.md) · 🇫🇷 Français · 🇬🇧 [English](README.en.md) · 🇪🇸 [Español](README.es.md)

L'aspect, le poids ressenti ou le son trompent souvent : l'aluminium et le zinc, gris et mats, sont constamment confondus. La **densité**, elle, est une propriété fixe du matériau et se mesure avec une simple balance de cuisine et un verre d'eau. Ce projet fournit le calculateur qui va avec.

![Méthode](https://img.shields.io/badge/M%C3%A9thode-Principe%20d'Archim%C3%A8de-2563eb)
![Durée](https://img.shields.io/badge/Dur%C3%A9e-5%20minutes-16a34a)
![Non destructif](https://img.shields.io/badge/%C3%89chantillon-non%20destructif-orange)

---

## 💡 Pourquoi la densité ?

| Métal | Densité (g/cm³) | Plage des alliages |
|---|---|---|
| Aluminium | 2,70 | 2,60 – 2,85 |
| Zinc | 7,14 | 6,60 – 7,14 |

Le zinc est **presque 2,6 fois plus dense** que l'aluminium. Les plages ne se chevauchent pas : la distinction est donc fiable. Aimant, son ou couleur ne sont que des indices.

## 🔬 Principe

Un échantillon plongé dans l'eau déplace un volume d'eau égal au sien. Si le récipient est posé sur la balance, celle-ci indique exactement la **masse de l'eau déplacée**. On en déduit le volume, puis la densité.

```
Densité = m / Δm × ρ_eau
```

| Symbole | Signification |
|---|---|
| `m` | Masse de l'échantillon sec (g) |
| `Δm` | Valeur affichée par la balance quand l'échantillon est suspendu dans l'eau (g) |
| `ρ_eau` | Masse volumique de l'eau, env. 0,998 g/cm³ à 20 °C |

## 🧰 Matériel

- Balance numérique (résolution de 0,1 g, suffisante dès env. 50 g d'échantillon)
- Récipient (verre ou bécher de 250–500 ml) rempli à moitié d'eau
- Fil fin et une tige ou un support pour le tenir
- Une goutte de liquide vaisselle (contre les bulles d'air)

## 📋 Procédure

1. **Peser l'échantillon sec** → noter `m`.
2. Poser le **récipient d'eau** sur la balance et **tarer** (0,0 g).
3. Attacher l'échantillon au fil et l'**immerger entièrement, suspendu librement**. Il ne doit toucher ni le fond ni les parois. Tenir le fil à la main ou sur un support.
4. **Chasser les bulles d'air**, attendre que l'affichage soit stable → noter `Δm`.
5. Saisir les valeurs dans le calculateur. C'est terminé.

> ⚠️ Si l'échantillon repose au fond, la balance affiche toute la masse `m`. La mesure est alors inutilisable.

## 🖥️ Le calculateur

Entrées :

- Masse sèche `m`
- Valeur de la balance `Δm`
- Température de l'eau (la masse volumique de l'eau est corrigée automatiquement)
- Résolution de la balance (pour l'incertitude)
- Facteur de sécurité `k` (1, 2 ou 3)

Sorties :

- Densité avec incertitude
- Volume de l'échantillon
- Matériaux compatibles du tableau
- Échelle montrant la valeur mesurée parmi les métaux connus

Fichier : `dichterechner.html`. Il fonctionne entièrement hors ligne dans le navigateur, sans installation. Disponible en **allemand, français, anglais et espagnol** (sélecteur en haut à droite).

## 📱 Installer comme application mobile

Le dossier `app/` (ou `dichterechner-app.zip`) contient une application web installable et utilisable hors ligne (PWA).

1. Placez les fichiers sur un hébergement HTTPS, p. ex. **GitHub Pages**, **Netlify Drop** ou **Cloudflare Pages** (glissez le dossier, vous obtenez un lien).
2. Ouvrez le lien sur votre téléphone.
3. **Android (Chrome) :** menu ⋮ → *Installer l'application* / *Ajouter à l'écran d'accueil*.
4. **iPhone (Safari) :** bouton Partager → *Sur l'écran d'accueil*.

Après le premier chargement, l'application fonctionne sans internet.

## 🔥 Pour qui fond ses propres alliages

La méthode est particulièrement utile pour la **fonte et l'alliage de métaux** : on vérifie sur la pièce coulée si le mélange correspond à ce qu'on visait. Exemple avec l'**or nordique** (Nordic Gold, utilisé pour les pièces de 10, 20 et 50 centimes d'euro) :

| Composant | Part en masse | Densité (g/cm³) |
|---|---|---|
| Cuivre | 89 % | 8,96 |
| Aluminium | 5 % | 2,70 |
| Zinc | 5 % | 7,14 |
| Étain | 1 % | 7,29 |

**Règle des mélanges :** la densité d'un alliage se calcule à partir des parts en masse `w` :

```
1 / ρ_alliage = Σ ( w_i / ρ_i )
```

Pour l'or nordique : `0,89/8,96 + 0,05/2,70 + 0,05/7,14 + 0,01/7,29 ≈ 0,1262` → **ρ ≈ 7,9 g/cm³**.

Vous pouvez comparer cette valeur théorique à la mesure de votre pièce coulée :

- **Valeur nettement plus basse** : porosité, retassures, bulles de gaz, ou trop d'aluminium.
- **Valeur nettement plus haute** : trop de cuivre, de zinc ou d'étain.
- **Valeur proche de la théorie** : le mélange et la coulée sont probablement bons.

> ℹ️ Avec quatre composants, la densité seule ne donne qu'une **indication**, pas la composition exacte. Plusieurs mélanges peuvent donner la même densité. Elle reste excellente pour détecter les erreurs grossières et les défauts de coulée. L'or nordique (≈ 7,9) a une densité proche de celle de l'acier, mais il n'est pas magnétique et sa couleur est dorée.

> 🦺 **Sécurité :** ne jamais plonger un morceau humide ou froid dans du métal en fusion (risque de projections). Travailler avec lunettes, gants et vêtements de protection, dans un endroit bien ventilé. Les fumées de zinc en particulier sont nocives. Mesurer la densité uniquement sur des pièces **refroidies** et sèches.

## 📊 Exemple

Échantillon de 100,0 g, eau à 20 °C, balance de 0,1 g :

| Valeur Δm | Densité | Résultat |
|---|---|---|
| 37,0 g | 2,70 g/cm³ | **Aluminium** |
| 14,0 g | 7,13 g/cm³ | **Zinc** |

Seuil de décision approximatif : **4,9 g/cm³**. En dessous, aluminium (ou magnésium/titane) ; au-dessus, zinc, acier ou métaux plus lourds.

## ⚠️ Sources d'erreur

- Les **bulles d'air** réduisent `Δm` et font monter la densité calculée.
- Un **fil épais** fausse le volume. Utiliser un fil le plus fin possible.
- Les **petits échantillons** (Δm inférieur à env. 10 g) sont imprécis, car la résolution de la balance pèse davantage.
- Les **cavités et la porosité** (pièces moulées) abaissent la densité mesurée.
- Les **revêtements** (galvanisé, anodisé, peint) peuvent légèrement décaler le résultat sur de petites pièces.
- Les **échantillons flottants** (densité inférieure à 1 g/cm³) ne sont pas mesurables avec cette méthode.

## 📈 Précision

L'incertitude se calcule à partir de la résolution de la balance :

```
δρ/ρ ≈ √( (δm/m)² + (δΔm/Δm)² )
```

Pour distinguer l'aluminium du zinc, une simple balance de cuisine suffit largement : l'écart est bien plus grand que l'incertitude de mesure.

## 🗂️ Matériaux inclus

Magnésium · Aluminium · Titane · Zinc · Étain · Acier/Fer · Laiton · Nickel · Cuivre · Plomb · Or nordique

D'autres métaux peuvent être ajoutés dans la liste `MAT` du code source (nom, minimum, maximum en g/cm³).

---

*Conçu pour tous ceux qui veulent savoir ce que contient vraiment leur pièce de métal.*
