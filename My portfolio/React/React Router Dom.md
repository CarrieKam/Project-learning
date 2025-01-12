#React 

----
## Install React Router
````bash
npm install react-router-dom
````

## Basic React Router Setup
common practice to alias (rename) BrowserRoute as simply 'Router' when it is imported

````js
import { BrowserRouter as Router } from 'react-router-dom';

export default function App() {
  return (
    <Router>
      {/* routes go here, as children */}
    </Router>
  );
}
````

## Route Component
declare routes within the Router component as children. We can declare as many routes as we like and we need to provide at least two props to each route, `path` and `component` (or `render`):

````js
import { BrowserRouter as Router, Route } from 'react-router-dom';

export default function App() {
  return (
    <Router>
      <Route path="/about" component={About} />
    </Router>
  );
}

function About() {
  return <>about</>   
}
````

The `path` prop specifies on what path of our app a given route is located.

For an about page, for example, we might want that route to be accessible on the path '/about'.

The `render` or `component` props are used to display a specific component for our path.

The `component` props can only receive a reference to a given component, whereas `render` is more typically used for applying some conditional logic to render one component or another. For render you can either use a reference to a component, or use a function:

````js
import { BrowserRouter as Router, Route } from "react-router-dom";

export default function App() {
  return (
    <Router>
      <Route path="/" render={() => <Home />} />
      <Route path="/about" component={About} />
    </Router>
  );
}

function Home() {
  return <>home</>;
}

function About() {
  return <>about</>;
}
````

It's worth noting that you can potentially drop the `render` or `component` prop entirely and use the component that you want to associate with a given route as a child of Route:

````js
import { BrowserRouter as Router, Route } from "react-router-dom";

export default function App() {
  return (
    <Router>
      <Route path="/about">
        <About />
      </Route>
    </Router>
  );
}
````

