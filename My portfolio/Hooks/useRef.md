#React 

----
Lets you reference a value that’s not needed for rendering
```javascript
const ref = useRef(initialValue)
```

By using a ref, you ensure that:
- **Store information** between re-renders (unlike regular variables, which reset on every render).
- Changing it **does not trigger a re-render** (unlike state variables, which trigger a re-render).
- **Information is local** to each copy of your component (unlike the variables outside, which are shared).

# How to use it (example)
```JavaScript
// Reference to dropdown element
const dropdownRef = useRef<HTMLDivElement>(null); 

//later in the return
return (
<div className="relative" ref={dropdownRef}>
)
```

----
Source:
https://react.dev/reference/react/useRef
