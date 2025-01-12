#tailwind 

----
```javascript
<button
key={name}
className="flex items-center px-3 py-2 rounded-lg text-xl relative overflow-hidden"
>

<img src={icon} alt={name} className="w-10 h-10 mr-2" />

{name}

<span className="absolute inset-0 border-[#A3466A] border-2 rounded-lg opacity-0 transition-opacity duration-100 hover:opacity-100"></span>

</button>
```

**Explanation:**
1. **`relative` and `absolute`:**
    - We make the button `relative` to position the border element absolutely within it.
    - The `span` element is positioned `absolute` within the button, covering its entire area.
      
2. **Border and Styling:**
    - The `span` has the `border-[#E3CAC6]` and `border-2` styles to create the desired border.
    - Initially, `opacity-0` makes the border invisible.
    - `hover:opacity-100` makes the border visible only on hover.
      
3. **Key Advantages:**
    - **No Layout Shifts:** The `span` element with the border doesn't affect the button's width or height.
    
- **`absolute`:**
    - This positions the `span` element absolutely within its parent (the button).
    - This means its position is relative to the top-left corner of the button, allowing us to precisely control its size and placement.

- **`inset-0`:**
    - This is a shorthand property that sets all four inset values (top, right, bottom, left) to `0`.
    - In combination with `absolute`, this makes the `span` element cover the entire area of the button.
      
- **`border-[#E3CAC6]`:**
    - This is a Tailwind CSS utility class that sets the border color to `#E3CAC6`.
      
- **`opacity-0`:**
    - This sets the initial opacity of the `span` to 0, making it invisible.
    
- **`transition-opacity`:**
    - This enables a smooth transition for the `opacity` property.
      
- **`duration-200`:**
    - This sets the duration of the opacity transition to 200 milliseconds, creating a visually pleasing effect.
      
- **`hover:opacity-100`:**
    - This class applies the `opacity-100` style (making the `span` fully visible) only when the button is hovered over.