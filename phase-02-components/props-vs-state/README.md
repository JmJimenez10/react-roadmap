# 🚀 02. Componentes - Props vs State

## 📋 Introducción
En React, **Props** y **State** son mecanismos clave para gestionar datos y renderizar componentes dinámicos.

* **Props (Propiedades):** Datos inmutables que un componente recibe desde su padre.
* **State (Estado):** Datos internos y dinámicos de un componente que pueden cambiar con el tiempo.

## 🧩 Ejemplo Comparativo

```js
import { useState } from 'react';

export const Saludo = ({ nombre }) => { // Props
  const [contador, setContador] = useState(0); // State

  return (
    <div>
      <h1>¡Hola, {nombre}!</h1>
      <p>Has hecho clic {contador} veces.</p>
      <button onClick={() => setContador(contador + 1)}>Incrementar</button>
    </div>
  );
};
```

## 💡 Diferencias Principales
* **Origen:** Las props vienen del componente padre; el state es interno del componente.
* **Modificación:** Las props son inmutables; el state es mutable mediante `useState()`.
* **Re-render** Cambios en state o props causan re-render automático.