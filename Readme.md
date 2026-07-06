# Vargas Vicente Ivonee Montserrat
#Instituto Tecnologico De Oaxaca
#PROGRAMACION WEB 

**Librería de componentes visuales interactivos en JavaScript puro**

##  Componentes reutilizables

Este proyecto incluye **dos componentes reutilizables** desarrollados con **JavaScript puro**:

-  **Modal**
-  **Toast**

Cada componente se invoca mediante una función y recibe parámetros personalizados como:

- Título
- Mensaje
- Tipo de notificación
- Texto de los botones
- Acciones personalizadas

Esto permite reutilizarlos fácilmente en cualquier página del proyecto sin necesidad de duplicar código.

---

##  Demo en vivo

 **GitHub Pages:**  
https://22161260-source.github.io/Act3-Componente/

---

##  Repositorio

 **GitHub:**  
https://github.com/22161260-source/Act3-Componente

---

## ¿Qué problema resuelve?

Cuando se construye una página con HTML/CSS/JS "a mano", es común terminar copiando y pegando el mismo modal de confirmación o el mismo aviso emergente en cada proyecto, con el texto quemado directamente en el HTML. **Faro.js** empaqueta ese patrón en dos funciones de JavaScript reutilizables:

- No hay que escribir el HTML del modal o del toast a mano cada vez; el componente construye su propia estructura visual.
- El contenido (título, mensaje, tipo de alerta, textos de los botones) se pasa como parámetro.
- Solo se necesitan dos archivos (`componente.css` y `componente.js`) para tener ambos componentes disponibles en cualquier proyecto.

---

## Instalación

1. Descarga o clona este repositorio:

https://github.com/22161260-source/Act3-Componente

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
#  Capturas de pantalla

##  Modal

<img width="617" height="221" alt="Modal" src="https://github.com/user-attachments/assets/5a0ae9a6-3cad-486b-ab0e-e27e0edb173a" />

---

##  Toast

<img width="624" height="171" alt="Toast" src="https://github.com/user-attachments/assets/ede97bc5-650f-47da-a61e-750c38e09811" />

---

##  Componente: Modal Eliminar Cuenta

<img width="248" height="123" alt="Modal Eliminar Cuenta" src="https://github.com/user-attachments/assets/5c0b1f39-c7cf-45aa-9081-df92bbfd7f7e" />

---

##  Toast - Notificación de Información

<img width="236" height="94" alt="Toast Información" src="https://github.com/user-attachments/assets/a78c74c7-af9c-4b3e-94cb-d226121e37f0" />

---

##  Toast - Notificación de Éxito

<img width="243" height="104" alt="Toast Éxito" src="https://github.com/user-attachments/assets/c7d0b3ce-7edd-4468-bb51-d036eda0a07d" />

---

##  Toast - Notificación de Error

<img width="279" height="95" alt="Toast Error" src="https://github.com/user-attachments/assets/b6cde54e-2007-4851-b754-57badb6c7c66" />

---

##  Toast - Notificación de Advertencia

<img width="223" height="88" alt="Toast Advertencia" src="https://github.com/user-attachments/assets/b80b7f90-e660-410b-b817-7c797f8babe8" />




## Estructura del repositorio

```

├── index.html            # Página de demostración con los 2 componentes
├── css/
│   └── componente.css    # Estilos del modal y el toast
├── js/
│   └── componente.js     # Lógica y API pública (window.Faro)
└── README.md
```

---

## Video demo 

[Ver video demo](https://drive.google.com/file/d/1ft5Gg8MlP-0VFjJ1wWOJHGKra1FWI29U/view?usp=sharing)

---


## Tecnologías

- HTML5 / CSS3
- JavaScript
