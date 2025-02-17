# 🚀 02. Componentes - JSX

## 📋 Introducción
JSX (JavaScript XML) es una extensión de JavaScript que permite escribir estructuras de UI de forma declarativa en React. Combina la lógica y el diseño en una sintaxis similar a HTML.

## 💡 Características de JSX
- **Expresiones en llaves:** Añade variables y funciones con `{}`
- **Etiquetas auto-cerradas:** Ejemplo: `<img />`
- **Clase como `className`:** JSX usa `className` en lugar de `class`
- **Comentarios en JSX:** Los comentarios deben estar dentro de `{}` y usarse como `/* comentario */`. Ejemplo: 
  ```jsx
  {/*
    Este es un comentario en JSX
  */}
  ```
- **Atributos en JSX:** Los atributos HTML como `href`, `src` y `alt` se usan normalmente, pero algunos cambian de nombre en JSX. Por ejemplo:
    - `class` --> `className`
    - `for` --> `htmlFor`
    - `style` --> `style={{}}` (se usa un objeto para los estilos en línea)

## 🔑 Claves adicionales de JSX
#### JSX es JavaScript
JSX no es HTML, es una sintaxis de JavaScript que se transpila a llamadas a React.createElement. Esto significa que puedes usar todo el poder de JavaScript dentro de JSX, incluyendo funciones, operadores y condiciones.

#### Renderizado de Arrays en JSX
Cuando se tiene un array de elementos, puedes renderizarlos usando .map(). Es importante asignar una key única para cada elemento al generar listas.

#### Fragmentos (`<></>`):
En JSX, puedes usar fragmentos para agrupar múltiples elementos sin añadir nodos adicionales al DOM. Esto es útil cuando necesitas devolver varios elementos, pero no quieres crear un nodo div extra. Ejemplo:
```js
return (
  <>
    <h1>Bienvenido</h1>
    <p>Este es un párrafo.</p>
  </>
);
```

## 🧩 Ejemplo: Condicionales y Map en JSX
```jsx
export const HelloComponent = () => {
  const tareas = ["Hacer proyecto en React", "Beber agua"];

  return (
    <ul>
      {tareas.length && tareas.map((tarea, index) => 
      <li key={index}>{tarea}</li>)}
    </ul>
  );
};
```

