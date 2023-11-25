<script>
    import { T } from '@threlte/core';
    import { createNoise2D } from 'simplex-noise'
    import { DirectionalLight, SphereGeometry } from 'three';

    const noise = createNoise2D();
    let geometry = new SphereGeometry(4, 32, 32);
    const vertices = geometry.getAttribute('position').array;

    for (let i = 0; i < vertices.length; i += 3) {
        const x = vertices[i];
        const y = vertices[i + 1];
        const z = vertices[i + 2];
        vertices[i + 2] = z + noise(x, y) * 0.5;
    }

    geometry.computeVertexNormals()
</script>

 <T.DirectionalLight position={[10, 10, 10]} />
 <T.HemisphereLight intensity={0.2} />

<T.Mesh
    geometry={geometry}
    position={[0, 0, 0]}
    rotation={[0, 0, 0]}
    scale={[1, 1, 1]}
>
</T.Mesh>


<T.GridHelper args={[50, 50]} />