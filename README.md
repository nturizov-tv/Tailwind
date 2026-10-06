Nashely Turizo Villareal codigo: 0192761
# Tecla: rediseño de una tienda de accesorios tech con Tailwind CSS

Taller de Desarrollo de Aplicaciones Web: "Rediseñando una Página Web". Es una página de una sola vista para una tienda ficticia de teclados, audífonos y mouse, con header, hero, grilla de 3 productos, formulario de contacto y footer.

## Cómo abrirla

No necesita instalación ni build. Basta con abrir `index.html` en el navegador con conexión a internet, porque Tailwind y las tipografías de Google Fonts se cargan por CDN.

```
taller-tailwind/
├── index.html
├── README.md
└── capturas/
    ├── desktop.png
    └── movil.png
```

## Por qué elegí Tailwind y no Bootstrap

Elegí **Opción A: Tailwind CSS**. Estas son las razones, en el orden en que pesaron.

**1. Personalización visual sin escribir CSS.** Bootstrap me deja cambiar variables de tema, pero el resultado se reconoce a simple vista como "una página Bootstrap". Con Tailwind definí mi propia paleta (grafito, hielo, menta y amarillo tecla) y mis dos tipografías una sola vez en `tailwind.config`, y todo el diseño sale de ahí. Eso aplica la práctica de personalizar el tema a nivel global y no elemento por elemento. Un detalle como el botón del hero, que se hunde al presionarlo como una tecla, lo resolví con clases utilitarias (`shadow-[...]`, `active:translate-y-1.5`) sin una sola línea de CSS propio. En Bootstrap habría tenido que sobrescribir estilos del componente `btn`, que es justo pelear contra el framework.

**2. Velocidad una vez que se domina la composición.** En la tabla comparativa de la clase, Tailwind sale con velocidad inicial "media" porque hay que componer las clases, y es cierto: al principio es más lento que copiar un componente de Bootstrap. Pero después de armar el patrón de una tarjeta, repetirlo para los tres productos fue copiar y cambiar texto, y los ajustes responsivos (`sm:`, `lg:`) se hacen en la misma línea, sin saltar a una hoja de estilos.

**3. Semántica HTML limpia.** Como Tailwind no impone componentes ni estructura, pude usar las etiquetas correctas: `header`, `nav`, `main`, `section`, `article` para cada producto, `footer`, y `label` enlazado a cada campo del formulario. No hay "divitis"; las clases solo describen el aspecto.

**4. Responsivo por defecto.** La grilla de productos pasa de 1 columna en móvil a 2 en tablet y 3 en escritorio con `grid sm:grid-cols-2 lg:grid-cols-3`, y el menú se colapsa en un botón de hamburguesa en pantallas pequeñas.

## Lo que me costó o no es ideal de Tailwind

**Densidad de clases.** La tabla de clase marca esto como punto débil y lo confirmé: las tarjetas tienen muchas clases y se repiten tres veces. En un proyecto real las encapsularía en un componente (React o Vue) o, si el patrón se repite mucho, en un `@apply` usado con moderación, como recomiendan las buenas prácticas. Para este taller, con una sola página en un solo archivo, preferí no sumar herramientas.

**Tamaño del CSS.** La clase indica que Tailwind produce menos de 10 KB gzipped gracias al purge, pero eso solo ocurre con un build (por ejemplo con Vite o la CLI de Tailwind). Aquí usé el **CDN a propósito**, porque el taller pide un único `index.html` funcional en 45 minutos, y el CDN descarga el compilador completo, así que mi página pesa más que esa cifra. Para producción haría el build con purge.

## Detalles de calidad

- Contraste de color revisado en textos y botones.
- Foco de teclado visible en enlaces, botones y campos.
- Animaciones desactivadas para quien tiene activada la preferencia de reducir movimiento.
- Formulario con validación nativa del navegador; al enviarlo solo muestra una confirmación en pantalla, no se conecta a ningún servidor.
# Tailwind
