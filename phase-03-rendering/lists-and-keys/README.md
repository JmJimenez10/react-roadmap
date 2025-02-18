# 🚀 03. Renderizado - Lists and Keys

## 📋 Introducción
En React, las **listas** se utilizan para mostrar múltiples elementos de forma dinámica, y las **keys** ayudan a identificar de manera única cada uno de esos elementos, optimizando el rendimiento durante las actualizaciones.

## 🧩 Ejemplo Básico: Renderizando Listas
```jsx
const nombres = ['Ana', 'Carlos', 'Marta'];

export const ListaNombres = () => {
  return (
    <ul>
      {nombres.map((nombre, index) => (
        <li key={index}>{nombre}</li>
      ))}
    </ul>
  );
};
```
En este ejemplo:
- `map()` crea una lista de elementos JSX.
- `key={index}` ayuda a React a identificar cada elemento.

## 💡 Importancia de las Keys

- **Identificación:** Las keys permiten que React actualice eficientemente solo los elementos necesarios.
- **Únicas:** Deben ser únicas entre elementos hermanos.
- **Advertencias:** Sin keys únicas, React muestra advertencias en la consola.

#### ✅ Correcto:
```jsx
items.map(item => <li key={item.id}>{item.nombre}</li>);
```

#### ⚠️ Puede ser incorrecto:
```jsx
items.map((item, index) => <li key={index}>{item.nombre}</li>);
```
*Usar índices como keys es aceptable solo para listas estáticas sin reordenamientos.*  
*Siempre que sea posible, usa identificadores únicos y estables.*