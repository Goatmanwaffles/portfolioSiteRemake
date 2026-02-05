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
     };

     let anchors: Anchor[] = [];
     let canvas: HTMLCanvasElement;

     function createParticle(minRadius: number, maxRadius:number): Particle{
          return{
               radius: Math.random() * (maxRadius - minRadius) + minRadius,
               angle: Math.random() * Math.PI * 2,
               speed: Math.random() * 0.0002 + 0.0001,
               size: Math.random() * 35+5,
               opacity: 0.4,
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
                    const x = anchor.x + Math.cos(p.angle) * p.radius;
                    const y = anchor.y + Math.sin(p.angle) * p.radius;

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

    function resizeCanvas() {
     if (!ctx || ctx == null) return;
        const dpr = window.devicePixelRatio || 1;
        const rect = canvas.getBoundingClientRect();

     canvas.width = canvas.clientWidth;
     canvas.height = canvas.clientHeight;


        ctx.scale(dpr, dpr);
        // Reinitialize anchors in layout pixels
        initializeAnchors(rect.width, rect.height, 35);
    }

    // Initial sizing
    resizeCanvas();

    // Optional: resize listener
    window.addEventListener('resize', resizeCanvas);

    // Start animation
    animate();

    // Cleanup listener on destroy
    return () => {
        window.removeEventListener('resize', resizeCanvas);
    };
    
});

</script>


     <canvas
  bind:this={canvas}
  class="absolute inset-0 z-0 w-full h-full pointer-events-none"
></canvas>