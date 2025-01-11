# Theme color toggle ()
#react  #tailwind #javascript

```jsx
// ✅ Valid: String interpolation in className
className={`base-class ${condition ? 'class-a' : 'class-b'}`}

// ❌ Invalid: Can't put components in className
className={`base-class ${condition ? <ComponentA/> : <ComponentB/>}`}

// ✅ Valid: Component rendering in JSX
{condition ? <ComponentA/> : <ComponentB/>}
```

The key rule is:
- Use string interpolation (`${...}`) for className when you need to conditionally apply classes
- Use JSX conditionals (`{...}`) when you need to conditionally render components

1. First approach (Working):
   ```jsx
   ${theme === 'dark' ? 'bg-[#A3466A]' : 'bg-[#3DB7CA]'}
```
This works because it's interpolating strings inside a template literal
- Both options are CSS class names (strings)
- The ternary returns a string in both cases
- Used properly inside a className template literal

2. Second approach (Not Working):
```jsx
<div className={`bg-black ${theme === 'dark' ? <Sun className="w-6 h-6" /> : <Moon className="w-6 h-6" />}`}/>
```
This doesn't work because:
- You're trying to interpolate JSX components (<Sun/> and <Moon/>) into a className string
- className expects a string, but you're giving it React components
- You can't render components inside a className attribute
- It's like trying to use HTML as a CSS class name, which isn't valid

3. Third approach (Working):
```jsx
{theme === 'dark' ? (
  <Sun className="w-6 h-6 text-black" />
) : (
  <Moon className="w-6 h-6 text-black" />
)}
```
This works because:
- It's proper JSX conditional rendering
- The ternary is directly in the JSX, not inside a className
- It returns React components, not strings
- Used for rendering components, not setting class names

---------------
# React can't have img string without import
#react #vite

In React, when using build tools like Vite or Create React app, you need to handle static assets like images differently than with regular HTML

## What you can do
1. Create a public folder and put all the picture there
2. Put this code:
```javascript 
useEffect(() => {
    // Import all images from the projects directory
    const images = import.meta.glob('../assets/projects/*.{png,jpg,jpeg,svg}', { eager: true });
    
    // Map over projects and replace image paths with actual imports
    const projectsWithImages = data.projects.project.map(project => {
      const imageName = project.imagePath.split('/').pop(); 
      const imagePath = imageName ? Object.entries(images).find(([path]) => path.includes(imageName)) : undefined;
      
      return {
        ...project,
        imagePath: imagePath ? (imagePath[1] as { default: string }).default : project.imagePath
      };
    });
```


