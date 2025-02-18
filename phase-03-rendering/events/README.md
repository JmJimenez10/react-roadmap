# 🚀 03. Renderizado - Events

## 📋 Introducción

En React, los **eventos** son manejadores que permiten responder a las interacciones del usuario, como clics, envíos de formularios, movimientos del mouse, y más. React envuelve los eventos nativos del navegador en un sistema propio conocido como **Synthetic Events**, que proporciona compatibilidad y un manejo uniforme de eventos en todos los navegadores.

## 💡 Características de los Eventos en React

- **Sintaxis de camelCase:** A diferencia del HTML tradicional, en React se usan nombres de eventos en camelCase (ej. `onClick` en lugar de `onclick`).
- **JSX y funciones:** En React, se pasa una función como manejador de eventos, no una cadena de texto.
- **Synthetic Events:** React envuelve los eventos nativos para garantizar la compatibilidad entre navegadores.
- **Prevent Default:** Se utiliza `e.preventDefault()` para evitar comportamientos por defecto.

## 🧩 Ejemplos de Manejo de Eventos

### 1. Evento `onClick`
```jsx
const Boton = () => {
  const manejarClick = () => {
    alert('¡Botón clickeado!');
  };

  return <button onClick={manejarClick}>Haz clic</button>;
};
```

### 2. Evento `onChange` en formularios
```jsx
const Formulario = () => {
  const [valor, setValor] = React.useState('');

  const manejarCambio = (e) => {
    setValor(e.target.value);
  };

  return (
    <input type="text" value={valor} onChange={manejarCambio} placeholder="Escribe algo..." />
  );
};
```

### 3. Prevenir comportamiento por defecto (`onSubmit`)
```jsx
const Formulario = () => {
  const manejarEnvio = (e) => {
    e.preventDefault();
    alert('Formulario enviado');
  };

  return (
    <form onSubmit={manejarEnvio}>
      <button type="submit">Enviar</button>
    </form>
  );
};
```

## 🛠️ Técnicas Comunes en Manejo de Eventos

### Eventos con Parámetros
```jsx
const Boton = ({ mensaje }) => {
  const mostrarAlerta = (mensaje) => {
    alert(mensaje);
  };

  return <button onClick={() => mostrarAlerta(mensaje)}>Mostrar Mensaje</button>;
};
```

### Eventos y Actualización de Estado
```jsx
const Contador = () => {
  const [contador, setContador] = React.useState(0);

  return (
    <div>
      <p>Contador: {contador}</p>
      <button onClick={() => setContador(contador + 1)}>Incrementar</button>
    </div>
  );
};
```

### Manejo de Múltiples Eventos
```jsx
const Caja = () => {
  const manejarMouseEnter = () => console.log('Mouse dentro');
  const manejarMouseLeave = () => console.log('Mouse fuera');

  return (
    <div
      onMouseEnter={manejarMouseEnter}
      onMouseLeave={manejarMouseLeave}
      style={{ padding: '20px', backgroundColor: '#f0f0f0' }}
    >
      Pasa el mouse por aquí
    </div>
  );
};
```

## 🔑 Beneficios del Manejo de Eventos en React
- **Consistencia:** Gracias a Synthetic Events, React proporciona una interfaz uniforme para todos los eventos.
- **Flexibilidad:** Se pueden pasar funciones anónimas, referenciadas o con parámetros según sea necesario.
- **Rendimiento:** React optimiza el manejo de eventos mediante la delegación de eventos.