<!-- YourComponent.svelte -->
<script>
    import Nav from "../Nav.svelte";
    let username = '';
    
    let password = '';
    
    let regSuccess = false;
  
    function handleSubmit() {
  if(username=='' && password=='')
  {
    alert('enter the creditinals ');
  }

 
  else{
    regSuccess=true;
  }

     
      // Perform a redirect to the login page if registration is successful
      if (regSuccess) {
        window.location.href = '/';
      }
    }
  
  </script>
  <Nav/>
  
  <main class="min-h-screen flex items-center justify-center">
    <div class="bg-white p-8 rounded-lg shadow-md max-w-md w-full md:max-w-lg">
      <h1 class="text-3xl font-semibold mb-6 text-center text-red-800">Login</h1>
      <form on:submit|preventDefault={handleSubmit} class="space-y-4">
        <div class="flex flex-col">
          <label for="username" class="mb-1">Username:</label>
          <input type="text" id="username" bind:value={username} class="border rounded px-3 py-2 w-full focus:outline-none focus:ring-2 focus:ring-blue-500" required />
        </div>
  
       
  
        <div class="flex flex-col">
          <label for="password" class="mb-1">Password:</label>
          <input type="password" id="password" bind:value={password} class="border rounded px-3 py-2 w-full focus:outline-none focus:ring-2 focus:ring-blue-500" required />
        </div>
  
       
  
        <button type="submit" class="bg-red-800 text-white px-4 py-2 rounded  focus:outline-none focus:ring-2 focus:ring-blue-500 focus:ring-offset-2">Login</button>
      </form>
    </div>
  </main>
  