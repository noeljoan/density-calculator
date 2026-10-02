# ⚖️ Calculadora de densidad de metales

**¿Aluminio o zinc? La balanza te lo dice con certeza.**

🇩🇪 [Deutsch](README.md) · 🇫🇷 [Français](README.fr.md) · 🇬🇧 [English](README.en.md) · 🇪🇸 Español

El aspecto, el peso o el sonido engañan: el aluminio y el zinc, grises y mates, se confunden constantemente. La **densidad** es una propiedad fija del material y se mide con una balanza de cocina y un vaso de agua. Este proyecto ofrece la calculadora para ello.

![Método](https://img.shields.io/badge/M%C3%A9todo-Principio%20de%20Arqu%C3%ADmedes-2563eb)
![Tiempo](https://img.shields.io/badge/Tiempo-5%20minutos-16a34a)
![No destructivo](https://img.shields.io/badge/Muestra-no%20destructivo-orange)

---

## 💡 ¿Por qué la densidad?

| Metal | Densidad (g/cm³) | Rango de aleaciones |
|---|---|---|
| Aluminio | 2,70 | 2,60 – 2,85 |
| Zinc | 7,14 | 6,60 – 7,14 |

El zinc es **casi 2,6 veces más denso** que el aluminio. Los rangos no se solapan, así que la distinción es fiable. Imán, sonido o color son solo indicios.

## 🔬 Principio

Una muestra sumergida en agua desplaza un volumen de agua igual al suyo. Con el recipiente sobre la balanza, esta muestra exactamente la **masa del agua desplazada**. De ahí se obtiene el volumen y luego la densidad.

```
Densidad = m / Δm × ρ_agua
```

| Símbolo | Significado |
|---|---|
| `m` | Masa de la muestra seca (g) |
| `Δm` | Lectura de la balanza con la muestra colgando libremente en el agua (g) |
| `ρ_agua` | Densidad del agua, aprox. 0,998 g/cm³ a 20 °C |

## 🧰 Material necesario

- Balanza digital (resolución de 0,1 g, suficiente para muestras desde unos 50 g)
- Recipiente (vaso o jarra medidora de 250–500 ml) medio lleno de agua
- Hilo fino y una varilla o soporte para sujetarlo
- Una gota de lavavajillas (contra las burbujas de aire)

## 📋 Procedimiento

1. **Pesar la muestra seca** → anotar `m`.
2. Colocar el **recipiente con agua** en la balanza y **tarar** (0,0 g).
3. Atar la muestra al hilo y **sumergirla por completo, colgando libremente**. No debe tocar el fondo ni las paredes. Sujetar el hilo con la mano o en un soporte.
4. **Quitar las burbujas de aire**, esperar a que la lectura sea estable → anotar `Δm`.
5. Introducir los valores en la calculadora. Listo.

> ⚠️ Si la muestra descansa en el fondo, la balanza muestra la masa total `m`. La medición es entonces inútil.

## 🖥️ La calculadora

Entradas: masa seca `m`, lectura `Δm`, temperatura del agua (la densidad del agua se corrige automáticamente), resolución de la balanza (para la incertidumbre) y factor de seguridad `k` (1, 2 o 3).

Salidas: densidad con incertidumbre, volumen de la muestra, materiales compatibles de la tabla y una escala que sitúa el resultado entre los metales conocidos.

La calculadora (`dichterechner.html`) funciona totalmente sin conexión en el navegador y está disponible en **alemán, francés, inglés y español** (selector arriba a la derecha).

## 📱 Instalar como app en el móvil

La carpeta `app/` (o `dichterechner-app.zip`) contiene una aplicación web instalable que funciona sin conexión (PWA).

1. Sube los archivos a cualquier alojamiento web con HTTPS, p. ej. **GitHub Pages**, **Netlify Drop** o **Cloudflare Pages** (arrastras la carpeta y obtienes un enlace).
2. Abre el enlace en el móvil.
3. **Android (Chrome):** menú ⋮ → *Instalar aplicación* / *Añadir a pantalla de inicio*.
4. **iPhone (Safari):** botón Compartir → *Añadir a pantalla de inicio*.

Tras la primera carga, la app funciona sin internet.

## 🔥 Para quien funde sus propias aleaciones

El método es especialmente útil para **fundir y alear**: se comprueba en la pieza colada si la mezcla coincide con el objetivo. Ejemplo con el **oro nórdico** (Nordic Gold, usado en las monedas de 10, 20 y 50 céntimos de euro):

| Componente | Fracción en masa | Densidad (g/cm³) |
|---|---|---|
| Cobre | 89 % | 8,96 |
| Aluminio | 5 % | 2,70 |
| Zinc | 5 % | 7,14 |
| Estaño | 1 % | 7,29 |

**Regla de las mezclas:** la densidad de una aleación se calcula con las fracciones en masa `w`:

```
1 / ρ_aleación = Σ ( w_i / ρ_i )
```

Para el oro nórdico: `0,89/8,96 + 0,05/2,70 + 0,05/7,14 + 0,01/7,29 ≈ 0,1262` → **ρ ≈ 7,9 g/cm³**.

Compara este valor teórico con la medición de tu pieza:

- **Claramente menor**: porosidad, rechupes, gases atrapados o demasiado aluminio.
- **Claramente mayor**: demasiado cobre, zinc o estaño.
- **Cercano al valor teórico**: la mezcla y la colada probablemente son buenas.

> ℹ️ Con cuatro componentes, la densidad solo da una **indicación**, no la composición exacta. Mezclas distintas pueden dar la misma densidad. Aun así es una prueba excelente para errores groseros y defectos de colada. El oro nórdico (≈ 7,9) tiene una densidad cercana a la del acero, pero no es magnético y es de color dorado.

> 🦺 **Seguridad:** nunca sumergir piezas húmedas o frías en metal fundido (salpicaduras). Usar gafas, guantes y ropa de protección, y ventilar bien. Los humos de zinc en particular son nocivos. Medir la densidad solo en piezas **enfriadas** y secas.

## 📊 Ejemplo

Muestra de 100,0 g, agua a 20 °C, balanza de 0,1 g:

| Lectura Δm | Densidad | Resultado |
|---|---|---|
| 37,0 g | 2,70 g/cm³ | **Aluminio** |
| 14,0 g | 7,13 g/cm³ | **Zinc** |

Umbral de decisión aproximado: **4,9 g/cm³**. Por debajo, aluminio (o magnesio/titanio); por encima, zinc, acero o metales más pesados.

## ⚠️ Fuentes de error

- Las **burbujas de aire** reducen `Δm` y aumentan la densidad calculada.
- Un **hilo grueso** falsea el volumen. Usar el más fino posible.
- Las **muestras pequeñas** (Δm inferior a unos 10 g) son imprecisas, porque la resolución de la balanza pesa más.
- Las **cavidades y la porosidad** (piezas fundidas) reducen la densidad medida.
- Los **recubrimientos** (galvanizado, anodizado, pintado) pueden desviar algo el resultado en piezas pequeñas.
- Las **muestras que flotan** (densidad inferior a 1 g/cm³) no se pueden medir con este método.

## 📈 Precisión

La incertidumbre se calcula a partir de la resolución de la balanza:

```
δρ/ρ ≈ √( (δm/m)² + (δΔm/Δm)² )
```

Para distinguir aluminio de zinc basta una balanza de cocina sencilla: la diferencia es mucho mayor que la incertidumbre.

## 🗂️ Materiales incluidos

Magnesio · Aluminio · Titanio · Zinc · Estaño · Acero/Hierro · Latón · Níquel · Cobre · Plomo · Oro nórdico

Se pueden añadir más metales en la lista `MAT` del código fuente (nombres, mínimo, máximo en g/cm³).

---

*Hecho para quienes quieren saber qué lleva realmente su pieza de metal.*

*© 2026 Noel Joan. Todos los derechos reservados.*
