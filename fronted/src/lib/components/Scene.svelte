<script>
  import { T, useFrame } from '@threlte/core'
  import { interactivity, OrbitControls } from '@threlte/extras'
  import { spring } from 'svelte/motion'
  import World from './World.svelte';
  import { DEG2RAD } from 'three/src/math/MathUtils'

  let autoRotate = false
  
  interactivity()
  const scale = spring(1)
  let rotation = 0
  useFrame((state, delta) => {
    rotation += delta
  })
</script>

<T.PerspectiveCamera
  makeDefault
  position={[0, 5, 10]}
>
  <OrbitControls
  autoRotate={autoRotate}
  enableZoom={false}
  maxPolarAngle={DEG2RAD * 80}
  />
</T.PerspectiveCamera>

<World
></World>

<T.DirectionalLight position={[0, 0, 0]} castShadow />

