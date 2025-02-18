# 🚀 03. Renderizado - High Order Components

## 📋 Introducción

En React, los **High Order Components (HOCs)** son un patrón avanzado para reutilizar la lógica entre componentes. Un HOC es una función que recibe un componente y devuelve un nuevo componente mejorado.

## 💡 Características de los HOCs
- **Reutilización de lógica:** Permiten compartir comportamiento entre múltiples componentes.
- **Composición de componentes:** Los HOCs se construyen mediante funciones que devuelven componentes.
- **Inmutabilidad:** No modifican el componente original, sino que crean uno nuevo.

## 🧩 Ejemplos de HOCs

### 1. Creación de un HOC básico
```jsx
const withColor = (WrappedComponent) => {
  return (props) => (
    <div style={{ border: '2px solid blue', padding: '10px' }}>
      <WrappedComponent {...props} />
    </div>
  );
};

const Mensaje = ({ texto }) => <h2>{texto}</h2>;

const MensajeConColor = withColor(Mensaje);

const App = () => <MensajeConColor texto="¡Hola desde un HOC!" />;
```

### 2. HOC para gestión de autenticación
```jsx
const withAuth = (WrappedComponent) => {
  return (props) => {
    const usuarioAutenticado = true; // Ejemplo
    return usuarioAutenticado ? <WrappedComponent {...props} /> : <p>Acceso denegado</p>;
  };
};

const Dashboard = () => <h2>Bienvenido al panel</h2>;
const DashboardProtegido = withAuth(Dashboard);

const App = () => <DashboardProtegido />;
```

## 🛠️ Técnicas y Buenas Prácticas con HOCs
- **Nombrado claro:** Usa nombres descriptivos (`withAuth`, `withLoading`).
- **Propagación de props:** Pasa todas las props al componente envuelto.
- **Evita HOCs anidados innecesarios:** Pueden dificultar la depuración.

## 🔑 Beneficios de los HOCs
- **Reutilización:** Centraliza lógica común.
- **Escalabilidad:** Facilita la extensión de componentes.
- **Separación de responsabilidades:** Divide la lógica y la interfaz.