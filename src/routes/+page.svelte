<div class="container">
    <div class="clock"></div>
    <img id="Q" src="img/SQ.svg" />
</div>

<style>

:global(body){margin:0;overflow:hidden}

@property --clock-hands-position {
    syntax: "<percentage>";
    inherits: false;
    initial-value: 100%;
}

img#Q{
    position: absolute;
    transform: rotate(0deg);
    transition: transform 2s ease-in-out;
}

.container{
    position: relative;
  width:100vw;
  height:100vh;
  display:flex;
  align-items:center;
  justify-content:center;
  overflow:hidden;
  background-image:url('https://images.unsplash.com/photo-1682685797661-9e0c87f59c60?ixlib=rb-4.0.3&ixid=M3wxMjA3fDF8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1740&q=80');
  background-size:cover;
  background-position:center;
    
}
.clock {
    transform:rotate(135deg);
    
    background-image: linear-gradient(to top, #85EEA5 0%, #85EEA5 100%);
    mix-blend-mode: normal;
  margin:-100vw;
  width:500vw;
  height:500vh;
    --clock-hands-position: 0%;
    --gradient-length: 100%;
    -webkit-mask-image: conic-gradient(
      black var(--clock-hands-position),
      transparent calc(var(--clock-hands-position)),
      transparent
    );  

    transition: --clock-hands-position 2s ease-in-out;
  
}
.clock:hover {
    --clock-hands-position: calc(1 * var(--gradient-length));
}

.clock:hover ~ img#Q {
    transform:rotate(360deg);
}

</style>