# 🚀 03. Renderizado - Refs

## 📋 Introducción
En React, **Refs** (abreviatura de referencias) permiten acceder y manipular directamente elementos del DOM o almacenar valores persistentes entre renders sin causar re-renderizados.

## 🧩 Ejemplo Básico: Enfocar un Input con useRef
```jsx
import { useRef } from 'react';

export const InputEnfocado = () => {
  const inputRef = useRef(null);

  const enfocarInput = () => {
    inputRef.current.focus();
  };
 
  return (
    <div>
      <input ref={inputRef} placeholder="Escribe algo..." />
      <button onClick={enfocarInput}>Enfocar</button>
    </div>
  );
};
```
#### 🔑 Aquí:
- `useRef()` crea una referencia.
- `inputRef.current` accede al elemento del DOM.
- `focus()` enfoca el input al hacer clic.

## 💡 Usos Comunes de Refs
- **Acceder al DOM:** Como inputs, botones o contenedores.
- **Almacenar valores persistentes:** Guardar valores entre renders sin re-renderizar.
- **Gestión de animaciones:** Controlar transiciones o integraciones con librerías externas.

## ⚠️ Buenas Prácticas
- Usa **Refs** solo cuando sea necesario.
- Prefiere **state** para controlar el flujo de la UI.