#React #ThreeJs #Gsap 

---------------

Add for Vanilla JS:
```html
<script src="https://cdnjs.cloudflare.com/.../three.module.min.js" integrity="sha512-2.." crossorigin="anonymous" referrerpolicy="no-referrer"></script>
```

# React with Three.js
Create easier 3D scenes = Three Fiber (library)
Ex:
```typescript
import React, {useRef} from 'react';
import {canvas, useFrame} from '@react-three/fiber';
import {Box} from 'react-three/dre:';

function RotatingBox() {
	const meshRef = useRef();
	
	// hooks
	useFrame(() => {
		meshRef.current.rotation.x += 0.01;
		meshRef.current.rotation.y += 0.01;
	})

	// React component
	return(
		<Box ref={meshRef} scale={[1,1,1]}>
			<meshBasicMaterial attach='material' color='green' />
		</Box>
	);
}
```

React Three Fiber acts as a wrapper 

# Gsap (animation)
```typescript
useGSAP(() => {
	gsap.to('#blue-box', {
		x: 250,
		repeat: -1,
		// animate reverse in circle
		yoyo: true,
		rotation: 360,
		// seconds
		duration: 2,
		// how the animation happens
		ease:'elastic'
	   // When it has to run
	}, []);
})
```