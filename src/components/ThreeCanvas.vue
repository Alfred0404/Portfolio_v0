<script setup>
import { ref, onMounted } from "vue";
import { Vector2, Vector3 } from "three";
import * as THREE from "three";
import { GLTFLoader } from "three/examples/jsm/loaders/GLTFLoader.js";
import { OrbitControls } from "three/examples/jsm/controls/OrbitControls.js";

const scene = new THREE.Scene();
function setup_camera() {
  const camera = new THREE.PerspectiveCamera(75, 1, 0.1, 1000);
  camera.position.set(0, 0, 7);
  camera.lookAt(0, -1, 0);
  return camera;
}

function setup_lights() {
  const ambientLight = new THREE.AmbientLight(0xffffff, 0.5);
  const sunLight = new THREE.DirectionalLight(0xffffff, 3);
  sunLight.position.set(-10, 3, 3);
  scene.add(sunLight);
  scene.add(ambientLight);
}

function load_wall_e_head() {
  const loader = new GLTFLoader().setPath("./src/assets/");
  loader.load("wall_e_head.glb", (gltf) => {
    const mesh = gltf.scene;
    mesh.position.set(0, 0, 0);
    mesh.scale.set(10, 10, 10);
    mesh.lookAt(new Vector3(0, 0, 1));
    objects.push(mesh);
    scene.add(mesh);
  });
}

const loader = new GLTFLoader().setPath("./src/assets/");
function load_wall_e_lens() {
  loader.load("wall_e_lens_eyes.glb", (gltf) => {
    const mesh = gltf.scene;
    mesh.position.set(0, 0, 0);
    mesh.scale.set(10, 10, 10);
    mesh.lookAt(new Vector3(0, 0, 1));
    objects.push(mesh);

    const material = new THREE.MeshPhysicalMaterial({
      color: 0xffffff,
      metalness: 1,
      roughness: 0,
      ior: 0.1,
      transmission: 0.5,
      thickness: 1,
      transparent: true,
      opacity: 0.7,
      clearcoat: 1,
      clearcoatRoughness: 0.2,
      reflectivity: 0.2,
    });
    mesh.material = material;
    scene.add(mesh);
  });
}

// ------------ THREE SETUP ------------- //

const target = ref();
const camera = setup_camera();
const renderer = new THREE.WebGLRenderer({ alpha: true, antialias: true });
// const controls = new OrbitControls(camera, renderer.domElement);

setup_lights();
const objects = [];
load_wall_e_head();
load_wall_e_lens();

const trackMouse = (event) => {
  const mousePosition = new Vector2();
  mousePosition.x = (event.clientX / window.innerWidth) * 2 - 1;
  mousePosition.y = -((event.clientY / window.innerHeight) * 2 - 1);
  const target = new Vector3(mousePosition.x, mousePosition.y, 5);
  objects.forEach((object) => object.lookAt(target));
};

function animate() {
  requestAnimationFrame(animate);
  renderer.render(scene, camera);
}

onMounted(() => {
  target.value.appendChild(renderer.domElement);
  const { clientWidth, clientHeight } = target.value;
  const aspectRatio = clientWidth / clientHeight;
  camera.aspect = aspectRatio;
  camera.updateProjectionMatrix();
  renderer.setSize(clientWidth, clientHeight);
  animate();
  window.addEventListener("resize", () => {
    const { clientWidth, clientHeight } = target.value;
    const aspectRatio = clientWidth / clientHeight;
    camera.aspect = aspectRatio;
    camera.updateProjectionMatrix();
    renderer.setSize(clientWidth, clientHeight);
  });
  window.addEventListener("mousemove", trackMouse);
});
</script>

<template>
  <div
    class="hidden lg:block xl:w-1/2"
    ref="target"
  ></div>
</template>
