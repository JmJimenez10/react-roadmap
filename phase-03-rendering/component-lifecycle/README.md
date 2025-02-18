# 🚀 03. Renderizado - Component Lifecycle

## 📋 Introducción
El **ciclo de vida** de un componente en React describe las etapas por las que pasa un componente desde su creación hasta su destrucción. Comprender este ciclo es esencial para gestionar actualizaciones, recursos y efectos secundarios.

## 🧩 Fases del Ciclo de Vida

- **Montaje (Mounting):** Ocurre al crear e insertar el componente.

    `useEffect(() => {}, [])`: Se ejecuta tras el primer render.

- **Actualización (Updating):** Cuando cambian props o state.

    `useEffect(() => {}, [dependencias])`: Se activa tras cada cambio en las dependencias.

- **Desmontaje (Unmounting):** Cuando se elimina el componente.

    `useEffect(() => { return () => { limpiar() } }, [])`: Realiza la limpieza.

## 🧩 Ejemplo Práctico
```jsx
import { useState, useEffect } from 'react';

export const Reloj = () => {
  const [hora, setHora] = useState(new Date().toLocaleTimeString());

  useEffect(() => {
    const intervalo = setInterval(() => {
      setHora(new Date().toLocaleTimeString());
    }, 1000);
    
    return () => clearInterval(intervalo); // Limpieza
  }, []);

  return <h1>Hora actual: {hora}</h1>;
};
```

## 💡 Resumen de Conceptos
- **Montaje:** Configura el estado inicial.
- **Actualización:** Reacciona a cambios en props o state.
- **Desmontaje:** Libera recursos.