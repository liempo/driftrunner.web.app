<script lang="ts">
	import { T } from '@threlte/core';
	import { Grid, OrbitControls } from '@threlte/extras';
</script>

<T.PerspectiveCamera
	makeDefault
	position={[-10, 10, 10]}
	fov={15}
>
	<OrbitControls
		autoRotate
		enableZoom={false}
		enableDamping
		autoRotateSpeed={0.5}
		target.y={1.5}
	/>
</T.PerspectiveCamera>

<!-- Create a long flat box like a road -->
<T.PlaneGeometry
	position={[-10, 0, 0]}
	rotation={[0, 0, 0]}
	scale={[20, 0.1, 2]}
	color="#ffffff"
/>

<Grid
	position.y={-0.001}
	cellColor="#ffffff"
	sectionColor="#ffffff"
	sectionThickness={0}
	fadeDistance={25}
	cellSize={2}
/>
