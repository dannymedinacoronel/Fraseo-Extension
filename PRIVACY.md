# Privacidad y permisos de Fraseo

*Actualizado: 27 de octubre de 2026 · Versión 1.3.0 · Responsable: Danny Medina Coronel ([empresademkor@gmail.com](mailto:empresademkor@gmail.com))*

## En pocas palabras

Fraseo no tiene cuentas, servidores propios, publicidad ni analítica. Las plantillas y preferencias se guardan en el almacenamiento local de la extensión en Chrome. Fraseo no las envía al desarrollador ni a nadie más.

## Qué se guarda y dónde

- El texto, formato, nombre, abreviatura, categoría, favorito, fechas y atajo de cada plantilla se guardan con `chrome.storage.local`.
- El tema visual, el idioma y tus preferencias (como la expansión de abreviaturas) se guardan en el mismo almacenamiento local.
- Fraseo cuenta cuántas veces usas cada plantilla y cuándo fue la última vez, solo para poder ordenarlas por uso. Ese contador no sale de tu navegador.
- Al exportar una copia, Fraseo crea un archivo JSON que tú eliges dónde guardar. Al importar, lee el archivo seleccionado para cargar sus plantillas.
- El contenido permanece en el perfil local de Chrome y no se sincroniza mediante `chrome.storage.sync`.

## Permisos y para qué se usan

| Permiso | Uso |
|---|---|
| Acceso a sitios web (`<all_urls>`) | Un pequeño script en las páginas recuerda el último campo editable y la posición del cursor, inserta el texto que eliges y muestra el formulario para rellenar campos. Se solicita para todos los sitios porque una plantilla puede usarse en cualquier página. Chrome permite limitar este acceso por sitio. |
| Abreviaturas | Mientras escribes en un campo editable, ese script compara en tu equipo los últimos caracteres antes del cursor con tus abreviaturas. No guarda lo que escribes, no lo envía a ningún sitio e ignora los campos de contraseña. Se puede desactivar en Ajustes → Expandir abreviaturas. |
| `storage` | Guardar y recuperar tus plantillas, ajustes, contador de uso y avisos de la extensión. |
| `contextMenus` | Mostrar tus plantillas al hacer clic derecho en un campo editable y guardar el texto seleccionado como plantilla nueva. |
| `sidePanel` | Abrir la interfaz de Fraseo junto a la página. |
| `clipboardWrite` | Solo cuando eliges copiar una plantilla. |
| `search` | Enviar al buscador predeterminado la consulta que confirmas desde las sugerencias de la barra de Chrome. |
| `scripting` y atajos | Insertar la plantilla que hayas asignado cuando Chrome detecta la combinación de teclas. |

## Cuándo sale texto de tu dispositivo

Fraseo no transmite las plantillas por sí mismo.

- Si eliges una sugerencia de Fraseo en la barra de direcciones, el texto seleccionado se envía al proveedor de búsqueda configurado en Chrome para realizar esa búsqueda.
- Si insertas una plantilla en un sitio web, ese sitio recibe el texto como si lo hubieras escrito allí.
- Si copias una plantilla, el sistema la coloca en el portapapeles del dispositivo.

## Control y eliminación

Puedes editar o eliminar plantillas desde Fraseo, exportar una copia, desactivar las abreviaturas o quitar la extensión desde Chrome. También puedes revisar el acceso a sitios en la configuración de la extensión. Quitar la extensión o borrar sus datos en Chrome puede eliminar las plantillas guardadas; conserva una copia exportada si quieres recuperarlas.

## Seguridad y alcance

Fraseo no incluye conexión a un servidor propio ni bibliotecas externas. Este aviso describe el comportamiento de la versión 1.3.0, se ofrece como información de privacidad y no sustituye la política del sitio web o del proveedor de búsqueda al que decidas enviar un texto.

## Contacto

Para consultas sobre privacidad: [empresademkor@gmail.com](mailto:empresademkor@gmail.com).
