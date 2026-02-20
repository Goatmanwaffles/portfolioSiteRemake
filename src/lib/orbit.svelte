<script lang="ts">
import { onMount } from 'svelte';


     type Anchor = {
          x: number;
          y: number;
          particles: Particle[];
     };
     
     type Particle = {
          radius: number;
          angle: number;
          speed: number;
          size: number;
          opacity: number;
          force: number;
     };

     let anchors: Anchor[] = [];
     let canvas: HTMLCanvasElement;
     let mouseX = 0;
     let mouseY = 0;
     let dpr = $state(1);

     

     function createParticle(minRadius: number, maxRadius:number): Particle{
          return{
               radius: Math.random() * (maxRadius - minRadius) + minRadius,
               angle: Math.random() * Math.PI * 2,
               speed: Math.random() * 0.0002 + 0.0001,
               size: Math.random() * 35+5,
               opacity: 0.4,
               force: 5,
          };
     }

     function createAnchor(x: number, y: number, particleCount:number): Anchor{
          const particles: Particle[] = [];

          for(let i = 0; i < particleCount; i++){
               particles.push(createParticle(150, 400))
          }

          return{
               x,
               y,
               particles
          };
     }

     function initializeAnchors(width:number, height:number, anchorCount:number){
          anchors.length = 0; //Clear existing anchors
          const particleCount = 5;
          
          for(let i = 0; i < anchorCount; i++){
               const x = Math.random() * width;
               const y = Math.random() * height;
               anchors.push(createAnchor(x, y, particleCount));
          };
     }

     function animate() {
          if(!canvas) return;
          const ctx = canvas.getContext('2d');
          if(!ctx) return;

          ctx.clearRect(0, 0, canvas.clientWidth, canvas.clientHeight);

          for(let i = 0; i < anchors.length; i++){
               const anchor = anchors[i]
               for(let j = 0; j < anchor.particles.length; j++){
                    const p = anchor.particles[j];

                    //Update Position
                    p.angle += p.speed;
                    let x = anchor.x + Math.cos(p.angle) * p.radius;
                    let y = anchor.y + Math.sin(p.angle) * p.radius;

                    //Apply mouse pull
                    const dx = mouseX - x;
                    const dy = mouseY - y;
                    const distance = Math.sqrt(dx * dx + dy * dy);
                    const maxDistance = 200;

                    if (distance < maxDistance && distance > 0) {
                         const force = (1 - distance / maxDistance) * p.force;
                         x -= (dx / distance) * force;
                         y -= (dy / distance) * force;
                         p.radius += (Math.sqrt(dx * dx + dy * dy) / distance) * force;
                    }

                    //Draw Particle
                    ctx.beginPath();
                    ctx.arc(x, y, p.size, 0, Math.PI * 2);
                    ctx.fillStyle = `rgba(255, 0, 255, ${p.opacity})`;
                    ctx.fill();
                    
               }
          }


          requestAnimationFrame(animate);
     }

     onMount(() => {
    if (!canvas) return;
    const ctx = canvas.getContext('2d');
    if (!ctx || ctx == null) return;

    // Set initial DPR value on client
    dpr = window.devicePixelRatio;

    function resizeCanvas() {
     if (!ctx || ctx == null) return;
        const dprValue = window.devicePixelRatio || 1;
        const displayWidth = canvas.clientWidth;
        const displayHeight = canvas.clientHeight;

        // Set the canvas pixel dimensions
        canvas.width = displayWidth * dprValue;
        canvas.height = displayHeight * dprValue;

        // Scale context to match device pixel ratio
        ctx.scale(dprValue, dprValue);

        // Reinitialize anchors in display pixels (not pixel dimensions)
        initializeAnchors(displayWidth, displayHeight, 35);
    }

    function handleMouseMove(e: MouseEvent) {
         const rect = canvas.getBoundingClientRect();
         mouseX = e.clientX - rect.left;
         mouseY = e.clientY - rect.top;
    }

    // Initial sizing
    resizeCanvas();

    
    window.addEventListener('resize', resizeCanvas);
    window.addEventListener('mousemove', handleMouseMove);

    // Start animation
    animate();

    // Run code whenever zoom (dpr) changes
    $effect(() => {
        dpr;
        resizeCanvas()
    });

    // Cleanup listener on destroy
    return () => {
        window.removeEventListener('resize', resizeCanvas);
        window.removeEventListener('mousemove', handleMouseMove);
    };
    
});

</script>

<svelte:window bind:devicePixelRatio={dpr} />


     <canvas
  bind:this={canvas}
  class="absolute inset-0 z-0 w-full h-full pointer-events-none"
></canvas>