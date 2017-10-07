<template>
  <div id="background" class="background" ref="background">
  </div>
</template>

<script type="text/ecmascript-6">
  import * as THREE from 'three'
  export default {
    name: 'background',
    mounted: function () {
      let SEPARATION = 120
      let AMOUNTX = 80
      let AMOUNTY = 80
      let container
      let camera, scene, renderer
      let particles = 0
      let particle = 0
      let count = 0
      let mouseX = 0
      let mouseY = 0
      let windowHalfX = window.innerWidth / 2
      init()
      animate()
      function init () {
        container = document.getElementById('background')
        // 放大比例 修改从75改为40
        camera = new THREE.PerspectiveCamera(40, window.innerWidth / window.innerHeight, 1, 10000)
        camera.position.z = 1000
        scene = new THREE.Scene()
        // eslint-disable-next-line no-array-constructor
        particles = new Array()
        let PI2 = Math.PI * 2
        let material = new THREE.ParticleCanvasMaterial({
          // 颜色
          color: 0x097BDB,
          program: function (context) {
            context.beginPath()
            context.arc(0, 0, 1, 0, PI2, true)
            context.fill()
          }
        })
        let i = 0
        for (let ix = 0; ix < AMOUNTX; ix++) {
          for (let iy = 0; iy < AMOUNTY; iy++) {
            particle = particles[i++] = new THREE.Particle(material)
            particle.position.x = ix * SEPARATION - ((AMOUNTX * SEPARATION) / 2)
            particle.position.z = iy * SEPARATION - ((AMOUNTY * SEPARATION) / 2)
            scene.add(particle)
          }
        }
        renderer = new THREE.CanvasRenderer()
        renderer.setSize(window.innerWidth, window.innerHeight)
        container.appendChild(renderer.domElement)
        document.addEventListener('mousemove', onDocumentMouseMove, false)
        window.addEventListener('resize', onWindowResize, false)
      }
      function onWindowResize () {
        windowHalfX = window.innerWidth / 2
        // windowHalfY = window.innerHeight / 2
        camera.aspect = window.innerWidth / window.innerHeight
        camera.updateProjectionMatrix()
        renderer.setSize(window.innerWidth, window.innerHeight)
      }
      function onDocumentMouseMove (event) {
        // 鼠标跟随 修改禁用y轴跟随,x轴/2.4
        mouseX = (event.clientX - windowHalfX) / 0.8
        // mouseY = event.clientY - windowHalfY
      }
      function animate () {
        requestAnimationFrame(animate)
        render()
      }
      function render () {
        camera.position.x += (mouseX - camera.position.x) * 0.05
        // y轴默认旋转 修改+100
        camera.position.y += (-mouseY - camera.position.y + 50) * 0.05
        camera.lookAt(scene.position)
        let i = 0
        for (let ix = 0; ix < AMOUNTX; ix++) {
          for (let iy = 0; iy < AMOUNTY; iy++) {
            particle = particles[i++]
            // 粒子位置 修改-500
            particle.position.y = (Math.sin((ix + count) * 0.3) * 50) + (Math.sin((iy + count) * 0.5) * 50) - 520
            // 粒子大小
            particle.scale.x = particle.scale.y = (Math.sin((ix + count) * 0.3) + 1) * 2 + (Math.sin((iy + count) * 0.5) + 1) * 2
          }
        }
        renderer.render(scene, camera)
        count += 0.1
      }
    }
  }
</script>


<style>
  .background {
    position: absolute;
    width: 100%;
    height: 100%;
    left: 0px;
    right: 0px;
    top: 0px;
    bottom: 0px;
  }
</style>

