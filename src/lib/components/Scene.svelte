<script lang="ts">
	import { T } from '@threlte/core'
	import { Grid, OrbitControls } from '@threlte/extras'
	import R34 from './models/R34.svelte'
</script>

<T.PerspectiveCamera
	makeDefault
	position={[-10, 5, 10]}
	fov={15}
>
	<OrbitControls enableDamping />
</T.PerspectiveCamera>

<T.DirectionalLight
	position={[0, 0, 0]}
	intensity={1.5}
/>
<T.DirectionalLight
	position={[0, 5, 0]}
	intensity={1.5}
/>
<T.DirectionalLight
	position={[-5, 0, 0]}
	intensity={1.5}
/>
<T.AmbientLight intensity={1} />

<!-- Car -->
<R34
	castShadow
	position={[0, 0, 0]}
	rotation={[0, -Math.PI / 2, 0]}
	paintColor="#191970"
	rimsColor="#C0C0C0"
/>

<!-- Ground -->
<T.Mesh
	position={[0, 0, 0]}
	rotation={[-Math.PI / 2, 0, 0]}
	receiveShadow
>
	<T.PlaneGeometry args={[5, 5]} />
	<T.MeshStandardMaterial
		color={'#000'}
		roughness={1}
	/>
</T.Mesh>

<Grid
	position.y={-0.001}
	cellColor="#ffffff"
	sectionColor="#ffffff"
	sectionThickness={2}
	fadeDistance={25}
	cellSize={1}
/>
