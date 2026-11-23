# Efectos y animaciones con CSS

Galería de ejercicios de un curso de diseño web para practicar cómo dar movimiento y efectos visuales a cajas con CSS. Cada caja representa un efecto distinto que se activa principalmente al pasar el puntero por encima.

El enlace a la demostración que figuraba originalmente en el repositorio es [Efectos y animaciones para cajas](https://fabiannorbertoescobar.github.io/Efectos-Animacions-Cajas-CSS/); su disponibilidad no está verificada.

## Tecnologías

- **HTML5:** estructura de la página y cajas de la galería.
- **CSS3:** estilos, transiciones, animaciones, transformaciones y adaptación a distintos anchos de pantalla.
- **Google Fonts:** fuente [Architects Daughter](https://fonts.google.com/specimen/Architects+Daughter), importada desde la hoja de estilos. Si no está disponible, se usa una fuente cursiva alternativa.

Es un sitio estático: no necesita JavaScript, frameworks, instalación de paquetes ni proceso de compilación.

## Qué vas a encontrar

La página reúne **63 cajas** con ejemplos de:

- **Bordes y formas:** expansión y recogida de bordes, esquinas redondeadas, elipses y triángulos.
- **Sombras y superficies:** sombras fijas, difuminadas y radiales; iluminación, transparencia, degradados y una esquina de página levantada.
- **Movimiento:** vibración, péndulo, balanceo, rebotes, giros, caídas, despegues y entradas o salidas deslizándose o rodando.
- **Transformaciones 3D:** giros sobre los ejes X e Y, perspectiva y traslaciones en tres dimensiones.
- **Combinaciones:** efectos como chicle, baile de girasol o achatamiento, que combinan transformaciones y cambios de opacidad.

Algunos efectos se ejecutan una vez y otros se repiten mientras se mantiene el puntero sobre la caja. La galería ajusta el ancho y los márgenes de las cajas mediante media queries.

## Conceptos de CSS practicados

| Recurso | Uso en los ejercicios |
| --- | --- |
| `:hover` | Activa cambios visuales, transiciones y animaciones. |
| `transition-duration` | Suaviza cambios como sombras, bordes y posición. |
| `@keyframes` y `animation` | Definen secuencias con diferentes etapas, duración y repeticiones. |
| `transform` y `transform-origin` | Trasladan, rotan, escalan e inclinan las cajas y modifican el punto de giro. |
| `perspective`, `rotateX`, `rotateY` y `translate3d` | Producen efectos de movimiento y profundidad. |
| `:before` y `:after` | Agregan detalles como triángulos, bordes y sombras sin elementos adicionales en el HTML. |
| `box-shadow`, `opacity`, `border-radius` y gradientes | Crean variaciones de superficie, transparencia y forma. |
| `@media` | Ajusta la presentación según el ancho de pantalla. |

Por ejemplo, el efecto «Flash» usa una animación por etapas para alternar la opacidad:

```css
.flash:hover {
    animation: 0.7s flash 1;
}

@keyframes flash {
    25%, 75% { opacity: 0; }
    50% { opacity: 1; }
}
```

La clase `flash` se combina con `caja` en el HTML; los estilos generales de los `div` definen el aspecto base de las cajas.

## Cómo probarlo

1. Cloná el repositorio y entrá a la carpeta:

   ```bash
   git clone https://github.com/FabianNorbertoEscobar/css-animations-transitions-ejercicios.git
   cd css-animations-transitions-ejercicios
   ```

2. Abrí `index.html` en un navegador y pasá el puntero sobre las cajas. No hace falta un servidor; la conexión a internet solo es necesaria para cargar la fuente externa.

También podés servirlo localmente, por ejemplo, si tenés Python 3 instalado:

```bash
python3 -m http.server 8000
```

Luego abrí `http://localhost:8000/`. Para probar la copia de `docs/`, abrí `http://localhost:8000/docs/`.

## Estructura

```text
.
├── index.html       # Galería de ejercicios
├── styles.css       # Estilos y animaciones
├── docs/
│   ├── index.html    # Copia de la galería
│   └── styles.css    # Copia de los estilos
├── monospace.json    # Configuración de vista previa del entorno
└── .vscode/          # Configuración del editor
```

Los archivos de `docs/` son copias de los de la raíz, no se generan automáticamente. Si modificás la galería y querés mantener ambas versiones iguales, actualizá las dos. `monospace.json` menciona `npm run dev`, pero el repositorio no incluye un `package.json` ni define ese comando; usá las opciones de ejecución indicadas arriba.

## Consideraciones

- Los ejemplos dependen principalmente de `:hover`: en pantallas táctiles y con navegación por teclado la interacción puede ser limitada. No hay un control específico para pausar el movimiento ni una adaptación a la preferencia de movimiento reducido.
- Algunas sombras radiales usan la sintaxis con prefijo `-webkit-`, por lo que su apariencia puede variar entre navegadores.
- Es una colección de prácticas: algunos efectos o declaraciones pueden comportarse de forma diferente según el navegador y no están presentados como componentes listos para producción.

## Autor

Fabián Escobar.
