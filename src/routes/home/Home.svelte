

<script>
  import Nav from "../Nav.svelte";
</script>

<style>
  /* Set full page background */
  body {
    margin: 0;
    padding: 0;
  }

  main {
    /* Set the background image and color */
    background-image: url('/src/images/bgnew.jpg');
    background-repeat: no-repeat;
    background-size:cover; /*Make the image cover the entire background area */
    background-position: center;/* Center the background image */
    min-height: 92vh;
  }
  
</style>

<Nav />

<main class="min-h-screen flex flex-col items-center justify-center  ">
  <h1 class="text-6xl text-black-800 mt-[-150px] text-bold ">Update with pen<span class="text-red-800">2</span>reel</h1>
  <p class="text-2xl text-black-600 mx-2 mt-4">Know latest tech-news in just one click</p>
  <button class="mt-4 bg-red-800 text-black-800 w-[100px] rounded-full"><a href="/cards">Explore</a></button>
  <!-- Your main content goes here -->
</main>



