<script lang="ts">
  import { onMount } from 'svelte'
  import * as THREE from 'three'
  onMount(() => {
    // Canvas
    const canvas = document.querySelector<HTMLCanvasElement>('canvas.webgl')

    // Sizes
    const sizes = {
      width: 800,
      height: 600
    }

    // Scene
    const scene = new THREE.Scene()

    // Object
    const cubeGeometry = new THREE.BoxGeometry(1, 1, 1)
    const cubeMaterial = new THREE.MeshBasicMaterial({
      color: '#2B6CB0'
    })
    const cubeMesh = new THREE.Mesh(cubeGeometry, cubeMaterial)
    scene.add(cubeMesh)

    // Camera
    const camera = new THREE.PerspectiveCamera(75, sizes.width / sizes.height)
    camera.position.z = 3
    scene.add(camera)

    // Renderer
    const renderer = new THREE.WebGLRenderer({
      canvas: canvas || undefined
    })
    renderer.setSize(sizes.width, sizes.height)
    renderer.render(scene, camera)
  })
</script>

<canvas class="webgl" />
