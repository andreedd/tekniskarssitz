<script>
  import svelteLogo from './assets/svelte.svg'
  import gearSmall from './assets/gear.png'
  import gearMedium from './assets/gearM.png'
  import gearLarge from './assets/gearL.png'
  import cornerLines from './assets/lines.png'
  import tfifLogo from './assets/TFiF-bla-logo-utan-text-digi.png'
  import Counter from './lib/Counter.svelte'
  import Countdown from './lib/Countdown.svelte'
  import Button from './lib/Button.svelte'
</script>

<main>
  <div class="corner-lines-right">
    <img src={cornerLines} alt="">
  </div>
  <div class="corner-lines-left">
    <img src={cornerLines} alt="">
  </div>
  <div class="corner-lines-bottom-right">
    <img src={cornerLines} alt="">
  </div>
  <div class="corner-lines-bottom-left">
    <img src={cornerLines} alt="">
  </div>
  <div class="gears">
    <div class="fade-3">
      <img class="gear-s" src={gearSmall} alt="gear">
    </div>
    <div class="fade-3">
      <img class="gear-s-2" src={gearSmall} alt="gear">
    </div>
    <div class="fade-2">
      <img class="gear-m" src={gearMedium} alt="gear">
    </div>
    <div class="fade-2">
      <img class="gear-m-2" src={gearMedium} alt="gear">
    </div>
    <div class="fade-1">
      <img class="gear-l" src={gearLarge} alt="gear">
    </div>
    <div class="fade-3">
      <img class="gear-s-3" src={gearSmall} alt="gear">
    </div>
  </div>

  <div class="text-content">
    <h1 class="main-header">TEKNISK ÅRSSITZ</h1>
    <h2 class="date-header">4 Februari 2023</h2>
    <div>
      <Countdown />
    </div>
    <Button />
    <div class="tfif-logo">
      <img src={tfifLogo} alt="tfif">
    </div>
  </div>
</main>

<style>
  main {
    color: #dfaf5d;
    text-align: center;
    display: flex;
    justify-content: center;
    flex-direction: column;
    display: flex;
    align-items: center;
  }

  .main-header {
    font-size: 3em;
  }

  .date-header {
    margin: 5px;
  }

  .tfif-logo img {
    width: 100px;
    margin-top: 5vh;
  }

  main .text-content {
    animation-name: fadeIn;
    animation-duration: 3000ms;
    display: flex;
    align-items: center;
    flex-direction: column;
  }

  .corner-lines-right img{
    position: absolute;
    width: 130px;
    height: 130px;
    top: 0;
    left: 0;
    transform: scaleX(-1);
  }

  .corner-lines-left img{
    position: absolute;
    width: 130px;
    height: 130px;
    top: 0;
    right: 0;
  }

  .corner-lines-bottom-left img{
    position: absolute;
    width: 130px;
    height: 130px;
    bottom: 0;
    left: 0;
    transform: scaleY(-1) scaleX(-1);
  }

  .corner-lines-bottom-right img{
    transform: scaleY(-1);
    position: absolute;
    width: 130px;
    height: 130px;
    bottom: 0;
    right: 0;
  }

  .gears {
    margin-top: 5vh;
    position: relative;
    height: 250px;
    width: 350px;
  }

  .fade-1 {
    animation-name: fadeIn;
    animation-duration: 3000ms;
  }

  .fade-2 {
    animation-timing-function: cubic-bezier(.48,-0.27,.67,-0.27);
    animation-name: fadeIn;
    animation-duration: 2000ms;
  }

  .fade-3 {
    animation-timing-function: cubic-bezier(.48,-0.27,.67,-0.27);
    animation-name: fadeIn;
    animation-duration: 4000ms;
  }

  .gear-s {
    animation-name: spinReverse;
    animation-duration: 8000ms;
    width: 70px;
    height: 70px;
    position: absolute;
    left: 42px;
    top: 130px;
  }

  .gear-s-2 {
    animation-name: spin;
    animation-duration: 4000ms;
    width: 60px;
    height: 60px;
    position: absolute;
    right: 17px;
    top: 65px;
  }

  .gear-s-3 {
    animation-name: spinReverse;
    animation-duration: 25000ms;
    width: 60px;
    height: 60px;
    position: absolute;
    left: 176px;
    top: 107px;
  }

  .gear-m {
    animation-name: spinReverse;
    animation-duration: 5000ms;
    width: 100px;
    height: 100px;
    position: absolute;
    right: 40px;
  }

  .gear-m-2 {
    animation-name: spinReverse;
    animation-duration: 5000ms;
    width: 100px;
    height: 100px;
    position: absolute;
    left: 40px;
    top: 0;
  }

  .gear-l {
    animation-name: spin;
    animation-duration: 20000ms;
    width: 200px;
    height: 200px;
    position: absolute;
    left: 0; 
    right: 0; 
    margin-left: auto; 
    margin-right: auto; 
  }

  .gears img {
    animation-iteration-count: infinite;
    animation-timing-function: linear; 
  }

  @keyframes spin {
    from {
        transform:rotate(0deg);
    }
    to {
        transform:rotate(360deg);
    }
}

@keyframes spinReverse {
    from {
        transform:rotate(0deg);
    }
    to {
        transform:rotate(-360deg);
    }
}

@keyframes fadeIn {
    from {
        opacity: 0;
    }
    to {
        opacity: 1;
    }
}

@media (min-width: 776px) {
  .corner-lines-right img{
    width: 250px;
    height: 250px;
  }

  .corner-lines-left img{
    width: 250px;
    height: 250px;
  }

  .corner-lines-bottom-left img{
    width: 250px;
    height: 250px;
  }

  .corner-lines-bottom-right img{
    width: 250px;
    height: 250px;
  }

  .main-header {
    font-size: 4em;
  }

  .tfif-logo img {
    width: 200px;
    margin-top: 35px;
  }

  .gears {
    height: 400px;
    width: 600px;
  }

  .gear-s {
    animation-duration: 7000ms;
    width: 100px;
    height: 100px;
    left: 66px;
    top: 270px;
  }

  .gear-s-2 {
    animation-duration: 3000ms;
    width: 70px;
    height: 70px;
    right: 30px;
    top: 115px;
  }

  .gear-s-3 {
    animation-name: spin;
    animation-duration: 7000ms;
    width: 100px;
    height: 100px;
    left: 20px;
    top: 190px;
  }

  .gear-m {
    animation-duration: 5000ms;
    width: 180px;
    height: 180px;
    right:50px;
    top: 0;
  }

  .gear-m-2 {
    animation-duration: 5000ms;
    width: 150px;
    height: 150px;
    left: 77px;
    top: 0;
  }

  .gear-l {
    animation-duration: 20000ms;
    width: 400px;
    height: 400px;
  }
}
</style>
