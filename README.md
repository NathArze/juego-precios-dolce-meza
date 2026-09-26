# 🎂 Dolce Meza · Aprende los Precios

Juego para memorizar el menú de **Dolce Meza**, al estilo Duolingo pero en rosa. Un solo archivo HTML, sin librerías ni instalación: ábrelo y a jugar.

👉 **[Jugar en línea](https://arauzsayuri-prog.github.io/juego-precios-dolce-meza/)**

## Cómo funciona

- **8 lecciones** en ruta: Clásicos I/II → Frutas → Postres → Especiales I/II → Gourmet → Repaso Maestro. Cada una se desbloquea al terminar la anterior y gana 1–3 estrellas según la precisión.
- **4 tipos de ejercicio**: opción múltiple, escribir el precio con teclado numérico, emperejar producto ↔ precio, y flashcards de estudio antes de cada lección nueva.
- **Progreso Duolingo**: corazones (5, se recargan solos cada 15 min), XP, nivel, racha diaria, meta diaria con anillo, combos y 8 insignias.
- **Pestaña Menú**: el recetario digital completo con buscador, para estudiar antes de practicar.
- Mascota de pastelo, sonidos con WebAudio, confeti y progreso guardado en `localStorage`.

En el teclado: `1-4` eligen opción, `Enter` comprueba o continúa.

## El menú que se memoriza

| Sección | Individual | Chico | Mediano | Grande |
|---|---|---|---|---|
| Pasteles Clásicos | $80 | $280 | $410 | $560 |
| Pastel de Frutas | $85 | $310 | $455 | $620 |
| Pasteles Especiales | $90 | $315 | $455 | $610 |

**Postres:** Choco Flan $250 · Cheese Cake $350 · Gelatina $210 · Mil Hojas $265

| Gourmet | Individual | Chico | Mediano | Grande |
|---|---|---|---|---|
| Piñón Rosa | $120 | $620 | $885 | $1,260 |
| Piñón Blanco | $100 | $340 | $485 | $680 |
| Baileys | $105 | $430 | $600 | $860 |

## Editar precios

Todos los datos viven en el bloque `MENU`, al inicio del `<script>` en `index.html`:

```js
{ id:"clasicos", tipo:"sabores", em:"🎂", titulo:"Pasteles Clásicos",
  sabores:[...], precios:{Individual:80, Chico:280, Mediano:410, Grande:560} }
```

Tipos disponibles:

- `sabores` — un precio por tamaño, varios sabores que comparten ese precio.
- `simple` — un solo producto con 4 tamaños (así está "Pastel de Frutas").
- `postres` — productos sueltos con precio único.
- `gourmet` — varios productos con 4 tamaños cada uno.

Al cambiar un precio se actualizan solos el menú digital, las preguntas y los distractores. En el ejercicio de emparejar solo se usan productos con **precios distintos**, para que ninguna pareja sea ambigua.
