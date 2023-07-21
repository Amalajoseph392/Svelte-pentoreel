<!-- YourComponent.svelte -->
<script>
  let navLinks = [
    { text: 'Home', url: '/' },
    { text: 'About', url: '/about' },
    { text: 'Register', url: '/register' },
    { text: 'Blogs', url: '/cards' },
    { text: 'Contact', url: '/contact' },
    
    
  ];
</script>

<style>
  /* Add any CSS styles for the logo image here (e.g., width, height, margin, etc.) */
  .logo-img {
    width: 100px;
    height: auto;
    margin-right: 20px;
  }
</style>

<div>
  <nav class="container mx-auto nav-bar p-4 flex items-center justify-between">
    <!-- Paste your logo image URL as the src attribute below -->
  
    <h1 class="text-black text-4xl font-bold px-5">pen<span class="text-red-800">2</span>reel</h1>
    <ul class="flex space-x-4 px-5">
      {#each navLinks as link}
        <li>
          <a href={link.url} class="text-red-800 font-bold">{link.text}</a>
        </li>
      {/each}
    </ul>
  </nav>
</div>
