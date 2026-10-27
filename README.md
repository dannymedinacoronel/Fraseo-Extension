# Fraseo

<p align="center"><img src="docs/icono.png" alt="Fraseo" width="96" /></p>

> Este repositorio contiene la información y los paquetes de instalación. El código fuente es privado.

**Fraseo** guarda los textos que escribes una y otra vez y los pega donde estés: con un clic desde el panel lateral de Chrome, con una abreviatura como `;hola` o con un atajo de teclado.

## Lo esencial

- **Abreviaturas.** Asigna una abreviatura a una plantilla y escríbela en cualquier campo de texto de una web: se sustituye por el texto al instante. Funciona en campos normales, áreas de texto y editores enriquecidos basados en `contenteditable`, también dentro de iframes. Empezar con `;` evita que salten sin querer.
- **Campos para rellenar.** Escribe `{{nombre}}`, `{{empresa}}` o cualquier otro nombre entre dobles llaves. Al usar la plantilla, Fraseo pide esos datos (en el panel o en un pequeño formulario dentro de la propia web) y muestra una vista previa.
- **Variables automáticas.** `{{fecha}}`, `{{hora}}` y `{{día}}` se sustituyen por la fecha, la hora y el día de la semana actuales. También funcionan en inglés y francés (`{{date}}`, `{{time}}`, `{{weekday}}`, `{{heure}}`, `{{jour}}`).
- **Formato.** Negrita, cursiva, subrayado, listas y enlaces se conservan al insertar en editores que admiten formato y al copiar. En campos de texto plano se inserta la versión sin formato.
- **Organización.** Categorías como filtros, favoritas siempre arriba, búsqueda que ignora tildes y resalta coincidencias, y orden por creación, uso, edición reciente o nombre. Cada plantilla muestra cuántas veces la has usado.
- **Atajos.** Tres ranuras (`Ctrl + Shift + 1/2/3` por defecto) insertan la plantilla asignada en el campo activo. `Alt + Shift + F` abre el panel. Puedes cambiarlos en `chrome://extensions/shortcuts`.
- **Clic derecho.** En un campo editable, el menú de Fraseo muestra tus plantillas agrupadas por categoría. Sobre un texto seleccionado, **Guardar selección en Fraseo** lo convierte en plantilla y abre el editor para que le pongas nombre.

## Instalar en Chrome

1. Ve a **[Releases](../../releases/latest)** y descarga `fraseo-1.3.0.zip`.
2. Descomprime el ZIP en una carpeta que no vayas a borrar (Chrome la lee desde ahí).
3. Abre `chrome://extensions` y activa el **Modo de desarrollador**.
4. Pulsa **Cargar descomprimida** y selecciona la carpeta descomprimida.
5. Pulsa el icono de Fraseo para abrir el panel lateral. La primera vez puedes elegir idioma y empezar con plantillas de ejemplo.

Requiere Chrome 120 o posterior. Instalada así no se actualiza sola: descarga el ZIP del último Release, sustituye la carpeta y pulsa el botón de recargar en `chrome://extensions`.

## Usar el panel

- **Nueva** (o la tecla `N`) abre el editor. `/` enfoca la búsqueda; las flechas recorren la lista e `Intro` usa la plantilla seleccionada (`Mayús + Intro` hace la acción contraria).
- Al pasar el ratón por una plantilla aparecen **Insertar**, **Copiar** y **Más acciones** (favorita, editar, duplicar, copiar para la barra de Chrome, atajo de teclado y eliminar).
- Pulsar una plantilla la copia al instante, aunque tenga campos: los `{{campos}}` se copian tal cual, y fecha, hora y día ya resueltos. Para rellenar los campos antes de copiar, usa el botón **Copiar** de la tarjeta. En **Ajustes → Al pulsar una plantilla** puedes hacer que el clic inserte en lugar de copiar.
- Al eliminar una plantilla aparece **Deshacer** durante unos segundos.
- **Insertar** escribe en el último campo que usaste en la página, aunque el foco esté en el panel.

## Ajustes

- **Apariencia:** Sistema, Claro, Noche o Rosa.
- **Idioma:** español, inglés o francés.
- **Expandir abreviaturas:** actívalo o desactívalo en todas las webs.
- **Copia de seguridad:** exporta un JSON con tus plantillas (incluidas abreviaturas, categorías, favoritas y atajos) o impórtalo. Al importar puedes añadir sin duplicar o reemplazar la biblioteca. Las copias de versiones anteriores siguen siendo compatibles.

## Límites conocidos

- Chrome no permite que las extensiones escriban en sus páginas internas (`chrome://…`), en la Chrome Web Store ni en la barra de direcciones. Ahí usa **Copiar** o **Copiar para la barra de Chrome** (después `Ctrl + L`, `Ctrl + V`).
- Google Docs y otros editores que dibujan el texto en un lienzo no exponen campos de texto, así que las abreviaturas no se expanden allí. Copiar y pegar sí funciona.
- Una abreviatura no puede empezar igual que otra (por ejemplo `;sal` y `;saludo`), porque la más corta se expandiría antes de terminar de escribir la larga. El editor avisa del conflicto.
- Las abreviaturas no se expanden en campos de contraseña.

## Privacidad

El aviso de privacidad está dentro de la extensión (Ajustes). Fraseo no tiene cuentas, analítica, publicidad ni servidores propios: plantillas, preferencias y el contador de uso se guardan en `chrome.storage.local`. Para detectar abreviaturas, Fraseo compara en tu equipo los últimos caracteres que escribes en un campo editable; no guarda ni envía lo que escribes. Al confirmar una sugerencia desde la barra de Chrome (palabra clave `fraseo`), la consulta se envía al buscador predeterminado. La web en la que insertas un texto lo recibe como si lo hubieras escrito.

## Permisos

| Permiso | Para qué |
|---|---|
| `storage` | Guardar plantillas, preferencias y contador de uso en tu navegador. |
| `sidePanel` | Mostrar el panel lateral. |
| `contextMenus` | Menú de clic derecho con tus plantillas. |
| `scripting` | Insertar el texto en la pestaña activa. |
| `clipboardWrite` | Copiar una plantilla al portapapeles. |
| `search` | Enviar al buscador la consulta de la barra de direcciones (`fraseo`). |
| `<all_urls>` | Detectar abreviaturas e insertar texto en cualquier web. |

## Autor

Danny Medina Coronel · empresademkor@gmail.com
