


  <script>
    import { onMount } from "svelte";
    import Nav from "../Nav.svelte";
  
    let searchTerm = "";
  
    /**
   * @type {any[]}
   */
    let posts = [];
  
    const getPosts = async () => {
      const res = await fetch('https://newsapi.org/v2/everything?q=tesla&from=2023-06-19&sortBy=publishedAt&apiKey=67fe9330ecd046e3af8482d6a680c647');
      const data = await res.json();
      const articles = data.articles;
      const filteredData = articles.slice(1, 100);
      posts = filteredData;
    };
  
    // Fetch posts on component mount
    onMount(() => {
      getPosts();
    });
  
    function filterItems() {
      if (searchTerm.trim() === "") {
        // If the search term is empty, show all posts
        posts = posts.slice();
      } else {
        posts = posts.filter(post => {
          const author = post.author ? post.author.toLowerCase() : "";
          const searchTermLowerCase = searchTerm.toLowerCase();
          return author.includes(searchTermLowerCase);
        });
      }
    }
  
    // This will update the filtered items whenever the search term changes
    $: filterItems();
  </script>
  
  
  
  <Nav/>
  
  <main class="container mx-auto">
    <div class="flex justify-center mt-8">
      <input
        type="text"
        placeholder="Search"
        class="border border-gray-400 rounded px-4 py-2 w-64"
        bind:value={searchTerm}
      />
      <button class="bg-red-800 text-white px-4 py-2 ml-2 rounded" on:click={filterItems}>
        Search
      </button>
    </div>
  
    <h1 class="text-red-800 text-6xl text-center mt-8">What's <span class="text-black">Happening?</span></h1>
    {#if posts.length === 0}
      <p class="text-center top-[20px] my-4 text-gray-500">Loading!....</p>
    {:else}
      <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4 mt-16">
        {#each posts as { author, title, description, url,urlToImage }}
          <div class="bg-white rounded-lg overflow-hidden shadow-md transition-transform transform hover:-translate-y-1">
             <img class="w-full h-40 object-cover object-center" src={urlToImage} alt={title} />
            <div class="p-4">
              <h1 class="text-xl font-semibold mb-2">{author}</h1>
              <h3 class="text-base text-gray-600 mb-4">{description}</h3>
              <a href={url} target="_blank" class="text-blue-500">Read more</a>
            </div>
          </div>
        {/each}
      </div>
    {/if}
  </main>
  
    