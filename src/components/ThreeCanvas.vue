<script setup>
import { ref, onMounted } from 'vue';
import * as THREE from 'three';
import GUI from 'lil-gui';


const gui = new GUI();

const params = {
    color: 0x3bd59d,
    spin: () => {
        cube.rotation.x += 0.05;
        cube.rotation.y += 0.05;
    },
    reset: () => {
        cube.rotation.x = 0;
        cube.rotation.y = 0;
    }

};

gui.addColor(params, 'color').onChange(() => {
    material.color.set(params.color);
});

gui.add(params, 'spin');



const target = ref();

const scene = new THREE.Scene();
const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);

const renderer = new THREE.WebGLRenderer({alpha: true, antialias: true});
renderer.setSize(300, 200);

const geometry = new THREE.BoxGeometry(1, 1, 1);
const material = new THREE.MeshBasicMaterial({ color: 0x3bd59d });
const cube = new THREE.Mesh(geometry, material);
scene.add(cube);

camera.position.z = 3;

function animate() {
  requestAnimationFrame(animate);

  cube.rotation.x += 0.01;
  cube.rotation.y += 0.01;

  renderer.render(scene, camera);
}

onMounted(() => {
  target.value.appendChild(renderer.domElement);
  animate();
});
</script>

<template>
    <!-- maybe place something that follows the mouse, or a moving camera around a scene, something interactive -->
  <div ref="target"></div>
</template>
