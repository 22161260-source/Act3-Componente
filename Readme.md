# Faro.js

**Librería de componentes visuales interactivos en JavaScript puro** (sin frameworks).

> Incluye 2 componentes reutilizables: **Modal** y **Toast**.
> Cada uno se llama con una función, recibiendo parámetros distintos (título, mensaje, tipo, textos de botones, etc.), por lo que puede insertarse en cualquier página sin reescribir el componente.

🔗 **Demo en vivo (GitHub Pages):** `https://TU-USUARIO.github.io/faro-js/`
🔗 **Repositorio:** `https://github.com/TU-USUARIO/faro-js`

---

## ¿Qué problema resuelve?

Cuando se construye una página con HTML/CSS/JS "a mano", es común terminar copiando y pegando el mismo modal de confirmación o el mismo aviso emergente en cada proyecto, con el texto quemado directamente en el HTML. **Faro.js** empaqueta ese patrón en dos funciones de JavaScript reutilizables:

- No hay que escribir el HTML del modal o del toast a mano cada vez; el componente construye su propia estructura visual.
- El contenido (título, mensaje, tipo de alerta, textos de los botones) se pasa como parámetro.
- Solo se necesitan dos archivos (`componente.css` y `componente.js`) para tener ambos componentes disponibles en cualquier proyecto.

---

## Instalación

1. Descarga o clona este repositorio:

   ```bash
   git clone https://github.com/TU-USUARIO/faro-js.git
   ```

2. Copia las carpetas `css/` y `js/` a tu proyecto (o solo los archivos `componente.css` y `componente.js`).

3. Inclúyelos en tu HTML, el CSS en `<head>` y el JS antes de cerrar `</body>`:

   ```html
   <head>
     ...
     <link rel="stylesheet" href="css/componente.css" />
   </head>
   <body>
     ...
     <script src="js/componente.js"></script>
   </body>
   ```

4. Listo. La librería expone un único objeto global: **`Faro`**, con dos métodos: `Faro.modal()` y `Faro.toast()`.

---

## Uso

### 1. Modal

```html
<button id="btn-eliminar">Eliminar cuenta</button>

<script>
  document.getElementById("btn-eliminar").addEventListener("click", () => {
    Faro.modal({
      title: "¿Eliminar tu cuenta?",
      content: "Esta acción no se puede deshacer.",
      confirmText: "Sí, eliminar",
      cancelText: "Cancelar",
      onConfirm: () => Faro.toast({ message: "Cuenta eliminada.", type: "error" }),
      onCancel: () => console.log("Cancelado"),
    });
  });
</script>
```

Parámetros disponibles:

| Parámetro | Tipo | Descripción |
|---|---|---|
| `title` | string | Título del modal |
| `content` | string / HTML / Node | Contenido del cuerpo |
| `confirmText` | string | Texto del botón principal |
| `cancelText` | string | Texto del botón secundario |
| `showCancel` | boolean | Muestra u oculta el botón de cancelar |
| `onConfirm` | function | Se ejecuta al confirmar |
| `onCancel` | function | Se ejecuta al cancelar o cerrar |

El modal también puede usarse solo para mostrar información, sin botón de cancelar:

```js
Faro.modal({
  title: "Términos de uso",
  content: "<p>Contenido en HTML si lo necesitas.</p>",
  confirmText: "Entendido",
  showCancel: false,
});
```

---

### 2. Toast

```html
<button id="btn-guardar">Guardar cambios</button>

<script>
  document.getElementById("btn-guardar").addEventListener("click", () => {
    Faro.toast({
      message: "Cambios guardados con éxito.",
      type: "success", // "info" | "success" | "error" | "warning"
      duration: 3000,
    });
  });
</script>
```

Parámetros disponibles:

| Parámetro | Tipo | Descripción |
|---|---|---|
| `message` | string | Texto que se muestra en la notificación |
| `type` | string | `"info"`, `"success"`, `"error"` o `"warning"` (cambia el color) |
| `duration` | number | Milisegundos antes de que el toast desaparezca solo |

Se pueden mostrar varios toasts al mismo tiempo; se apilan automáticamente en la esquina inferior derecha.

---

## Estructura del repositorio

```
faro-js/
├── index.html            # Página de demostración con los 2 componentes
├── css/
│   └── componente.css    # Estilos del modal y el toast
├── js/
│   └── componente.js     # Lógica y API pública (window.Faro)
├── img/
│   └── icono-faro.svg    # Ícono/favicon usado en la demo
└── README.md
```

---

## Capturas de pantalla

> Reemplaza estas imágenes por las tuyas propias (súbelas a `img/` y enlázalas aquí).

| Modal abierto | Toast de éxito |
|---|---|
| ![Modal de Faro.js](img/captura-modal.png) | ![Toast de Faro.js](img/captura-toast.png) |

---

## Video demo 

[Ver video demo](https://drive.google.com/file/d/1ft5Gg8MlP-0VFjJ1wWOJHGKra1FWI29U/view?usp=sharing)



---

## Cómo activar GitHub Pages

1. Entra a tu repositorio en GitHub → **Settings → Pages**.
2. En **Source**, selecciona la rama `main` y la carpeta `/root`.
3. Guarda. GitHub te dará una URL como `https://tu-usuario.github.io/faro-js/`.
4. Esa es la URL que debes entregar junto con el link del repositorio.

---

## Tecnologías

- HTML5 / CSS3
- JavaScript (Vanilla, ES6+) — sin frameworks ni dependencias externas
