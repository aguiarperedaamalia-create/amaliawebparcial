Biblioteca Digital

Esta es mi biblioteca digital para el primer parcial de Programación Web. Es una sola página con cuatro vistas (catálogo, mis préstamos, agregar libro y resumen) que se cambian desde el menú sin recargar. Está hecha con HTML, CSS y JavaScript puro, sin librerías ni frameworks.

Esta carpeta es la fase 2 y cubre los requisitos generales del 1 al 6: menú de navegación, SEO y accesibilidad, diseño responsivo, tema claro y oscuro, transiciones y animaciones, y persistencia con localStorage. Al recargar se conservan los libros, los préstamos, el tema, el nombre del usuario y el orden elegido en el catálogo.

Todavía faltan los modales propios, que llegan en la fase 3. Mientras tanto, el botón Prestar usa el nombre guardado en Resumen y ajustes, y el botón Eliminar aún no existe.

Cómo abrirlo

Basta con abrir index.html en el navegador. No hace falta servidor ni instalar nada.

Qué hay en cada carpeta

index.html tiene la estructura de las cuatro vistas.
css/styles.css tiene todos los estilos, los dos temas y los puntos de quiebre del diseño responsivo.
assets/logo.svg es el logotipo, que también se usa como icono de la pestaña.

Dentro de js/ cada archivo tiene una sola responsabilidad:

fechas.js hace las cuentas con fechas (hoy, sumar días, diferencia entre fechas).
logica.js guarda las reglas del negocio: prestar, devolver, validar, agregar, editar, filtrar y ordenar. No toca la pantalla ni el navegador.
datos.js crea los libros y préstamos iniciales a partir de la fecha de hoy.
almacenamiento.js lee y escribe en localStorage.
ui.js dibuja la interfaz a partir de los datos que recibe.
app.js une todo: escucha los eventos, llama a las reglas, guarda y vuelve a dibujar.

Cómo se guardan los datos

Solo hay dos colecciones: libros y prestamos. Un libro no guarda si está prestado ni a quién, eso se averigua buscando su préstamo activo. Tampoco se guardan los días de retraso ni si un libro está vencido, todo eso se calcula cada vez. Devolver un libro no borra el préstamo, solo le anota la fecha de devolución, así el historial se conserva.
