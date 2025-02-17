# 🚀 03. Componentes - Composition

## 📋 Introducción

La **composición** es un patrón clave en React que permite construir interfaces de usuario reutilizables y modulares mediante la combinación de componentes más pequeños. En lugar de depender únicamente de la herencia, React fomenta la creación de componentes independientes que pueden ser combinados para formar interfaces complejas.

## 💡 Características de la Composición

- **Composición en lugar de herencia:** React utiliza composición de componentes, lo que significa que se construyen componentes más pequeños que pueden ser reutilizados y combinados en componentes más grandes.
- **Propagación de props:** Los componentes pueden recibir `props` desde sus componentes padres para personalizar su comportamiento y contenido.
- **Children en React:** React tiene una propiedad especial llamada `children` que permite a los componentes padres pasar contenido dentro de los componentes hijos.

## 🧩 Ejemplo de Composición

### 1. Composición básica con props

```jsx
// Componente hijo
const Bienvenida = ({ nombre }) => {
  return <h1>Bienvenido, {nombre}!</h1>;
};

// Componente padre
const App = () => {
  return <Bienvenida nombre="Juan" />;
};
```

### 2. Composición utilizando children

```jsx
// Componente de Layout que acepta contenido a través de `children`
const Layout = ({ children }) => {
  return (
    <div>
      <header>Mi aplicación</header>
      <main>{children}</main>
      <footer>Derechos reservados</footer>
    </div>
  );
};

// Componente que utiliza `Layout` para componer una interfaz
const App = () => {
  return (
    <Layout>
      <h1>Contenido de la página</h1>
      <p>Este es el contenido que pasa el componente hijo.</p>
    </Layout>
  );
};
```

## 🛠️ Técnicas de Composición Comunes

### Composición con Props

Puedes personalizar el comportamiento de los componentes hijos pasándoles props desde el componente padre.

```jsx
const Boton = ({ color, texto }) => {
  return <button style={{ backgroundColor: color }}>{texto}</button>;
};

const App = () => {
  return (
    <div>
      <Boton color="blue" texto="Aceptar" />
      <Boton color="red" texto="Cancelar" />
    </div>
  );
};
```

### Componentes Funcionales vs. Componentes de Orden Superior

- **Componentes funcionales:** Son componentes más simples que se componen principalmente de funciones que devuelven JSX.
- **Componentes de orden superior (HOCs):** Son funciones que toman un componente y devuelven un nuevo componente. Esto permite la reutilización de la lógica en varios componentes.

```jsx
const withColor = (Component) => {
  return (props) => <Component {...props} color="blue" />;
};

const Boton = ({ color, texto }) => {
  return <button style={{ backgroundColor: color }}>{texto}</button>;
};

const BotonConColor = withColor(Boton);

const App = () => {
  return <BotonConColor texto="Enviar" />;
};
```

### Composición con Render Props

Las **Render Props** son un patrón donde un componente pasa una función como prop a un hijo. Esto permite una mayor flexibilidad en la forma en que los hijos se renderizan.

```jsx
const Contador = ({ render }) => {
  const [contador, setContador] = React.useState(0);

  return (
    <div>
      <button onClick={() => setContador(contador + 1)}>Incrementar</button>
      {render(contador)}
    </div>
  );
};

const App = () => {
  return <Contador render={(contador) => <p>El contador es: {contador}</p>} />;
};
```

## 🔑 Beneficios de la Composición
- **Reutilización de componentes:** La composición permite construir aplicaciones modulares y reutilizables. Cada componente tiene una única responsabilidad, lo que facilita su reutilización en diferentes partes de la aplicación.
- **Mayor legibilidad y mantenimiento:** La descomposición de la interfaz en componentes pequeños y aislados mejora la claridad y simplifica el mantenimiento.
- **Flexibilidad:** Puedes personalizar componentes mediante props, lo que hace que los componentes sean más dinámicos y fáciles de extender.
