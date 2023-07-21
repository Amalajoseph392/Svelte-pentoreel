<!-- Blogs.svelte -->

<script>
    import { onMount } from 'svelte';
  
    /**
   * @type {any[]}
   */
    let blogs=[]; // Initialize with an empty array
  
    // Fetch data from the API when the component is mounted
    onMount(async () => {
      try {
        const response = await fetch('https://newsapi.org/v2/everything?q=tesla&from=2023-06-19&sortBy=publishedAt&apiKey=67fe9330ecd046e3af8482d6a680c647'); // Replace with the actual API URL
        if (response.ok) {
          blogs = await response.json();
        } else {
          console.error('Failed to fetch blogs:', response.status);
        }
      } catch (error) {
        console.error('Error fetching blogs:', error);
      }
    });
  </script>
  
  <main class="container mx-auto p-4">
    {#each blogs as blog}
      <div class="blog-card">
        <h2>{blog.title}</h2>
        <p>{blog.description}</p>
      </div>
    {/each}
  </main>
  
  <style>
    /* Add some styling to the blogs */
    .blog-card {
      border: 1px solid #ccc;
      padding: 10px;
      margin: 10px 0;
    }
  </style>
  