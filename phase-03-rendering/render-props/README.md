# 🚀 03. Renderizado - Render Props

## 📋 Introducción
**Render Props** es un patrón avanzado en React que permite a los componentes compartir lógica reutilizable a través de una función que se pasa como prop.

## 🧩 Ejemplo Básico: Contador con Render Props
```jsx
export const Contador = ({ render }) => {
  const [contador, setContador] = useState(0);

  const incrementar = () => setContador(contador + 1);

  return <div>{render(contador, incrementar)}</div>;
};

export const Ejemplo = () => {
  return (
    <Contador 
      render={(contador, incrementar) => (
        <>
          <h1>Contador: {contador}</h1>
          <button onClick={incrementar}>Incrementar</button>
        </>
      )} 
    />
  );
};
```

## 💡 Ventajas de Render Props
- **Reutilización de lógica:** Comparte comportamiento entre múltiples componentes.
- **Composición flexible:** Personaliza la interfaz según la necesidad.

## ⚠️ Buenas Prácticas:
- Usa nombres claros como `render` o `children` para la prop.
- Mantén el código legible evitando anidamientos complejos.