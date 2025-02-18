# 🚀 02. Componentes - Conditional Rendering

## 📋 Introducción

El **renderizado condicional** es una técnica que permite a React mostrar u ocultar componentes según una lógica específica. Esta capacidad es clave para crear interfaces dinámicas y adaptativas.

## 🧩 Ejemplo Básico: Mensaje.jsx

```js
export const Mensaje = ({ usuario }) => {
  return (
    <div>
      {usuario ? (
        <h1>Bienvenido, {usuario}</h1>
      ) : (
        <h1>Por favor, inicia sesión</h1>
      )}
    </div>
  );
};
```

## 💡 Formas de Renderizado Condicional

- **Operador Ternario:** Ideal para renderizados cortos.
  ```js
  const mostrar = false
  ---
  <div className={`mostrar ? "show" : "hide"`}>
  ```
- **&& (AND lógico):** Muestra contenido solo si la condición es verdadera
  ```js
    const marca = "Nike"
    ---
    <div>
        {marca === "Nike" && (
            <p>La marca es Nike</p>
        )}
    </div>
  ```
- **if/else:** Para condiciones más complejas

  ```js
  const MiComponente = ({ usuarioAutenticado }) => {
    let contenido;

    if (usuarioAutenticado) {
      contenido = <h1>Bienvenido de nuevo, usuario!</h1>;
    } else {
      contenido = <h1>Por favor, inicia sesión.</h1>;
    }

    return <div>{contenido}</div>;
  };
  ```
