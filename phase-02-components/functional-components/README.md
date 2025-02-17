# 🚀 02. Componentes - Functional Components

## 📋 Introducción

Los **Functional Components** son funciones de JavaScript que retornan JSX para renderizar elementos en pantalla. Son más simples y eficientes que los componentes de clase.

## 🧩 Ejemplo Básico: HelloComponent.jsx

```js
export const HelloComponent = () => {
  return (
    <div>
      <h1>Hello from HelloComponent</h1>
    </div>
  );
};
```

## 🧩 Ejemplo con Estado (useState): Counter.jsx

```js
import { useState } from "react";

export const HelloComponent = () => {
  const [count, setCount] = useState(0);

  return (
    <div>
      <h2>Contador: {count}</h2>
      <button onClick={() => setCount(count + 1)}>Incrementar</button>
    </div>
  );
};
```
