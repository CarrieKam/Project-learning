## React Router
 for routing among various view components in React applications. It helps keep the user interface in sync with the URL. In addition, React Router allows defining which view to display for a specified URL. 
 
 core package containing standard components and functionalities to implement routing in React applications

The three main packages related to React Router are:
- [react-router](https://www.npmjs.com/package/react-router "react-router NPM package"): Contains the core functionality of React Router, including route-matching algorithms and hooks.
- [react-router-dom](https://www.npmjs.com/package/react-router-dom "react-router-dom NPM package"): Includes everything in **react-router** and adds a few DOM-specific APIs.
- [react-router-native](https://www.npmjs.com/package/react-router-native "react-router-native NPM package"): Includes everything in **react-router** and adds a few React Native-specific APIs.

## React Router DOM
- dynamic routing in web applications
- supports component-based routing, which is the ideal solution for routing if the React application is running on the browser


## ### When to Use Which
If you are working on a web application, the better option is to use **react-router-dom**, because it contains all the necessary common components and features essential for routing in a web application. **react-router-dom** installs **react-router** as a dependency, so there is no need to re-install and import anything directly from the **react-router**.

Even on mobile applications with React Native, **react-router-native** is enough, for the same reason as **react-router-dom** is enough in web apps.

Because of that, there is no need to import the **react-router** package directly anywhere, as **react-router-dom** and **react-router-native** provide all the required functionalities.

-------------
Sources:
- https://www.syncfusion.com/blogs/post/react-router-vs-react-router-dom
