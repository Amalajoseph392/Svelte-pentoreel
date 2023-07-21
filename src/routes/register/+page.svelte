<!-- YourComponent.svelte -->
<script>
  import Nav from "../Nav.svelte";
  let username = '';
  let email = '';
  let password = '';
  let cpassword = '';
  let regSuccess = false;

  function handleSubmit() {
    if (password === cpassword) {
      regSuccess = true;
      // Perform a redirect to the login page if registration is successful
      if (regSuccess) {
        window.location.href = '/login';
      }
    } else {
      alert('Passwords do not match, try again.');
    }
  }
</script>
<Nav/>

<main class="min-h-screen flex items-center justify-center">
  <div class="bg-white p-8 rounded-lg shadow-md max-w-md w-full md:max-w-lg">
    <h1 class="text-3xl font-semibold mb-6 text-center text-red-800">Register</h1>
    <form on:submit|preventDefault={handleSubmit} class="space-y-4">
      <div class="flex flex-col">
        <label for="username" class="mb-1">Username:</label>
        <input type="text" id="username" bind:value={username} class="border rounded px-3 py-2 w-full focus:outline-none focus:ring-2 focus:ring-blue-500" required />
      </div>

      <div class="flex flex-col">
        <label for="email" class="mb-1">Email:</label>
        <input type="email" id="email" bind:value={email} class="border rounded px-3 py-2 w-full focus:outline-none focus:ring-2 focus:ring-blue-500" required />
      </div>

      <div class="flex flex-col">
        <label for="password" class="mb-1">Password:</label>
        <input type="password" id="password" bind:value={password} class="border rounded px-3 py-2 w-full focus:outline-none focus:ring-2 focus:ring-blue-500" required />
      </div>

      <div class="flex flex-col">
        <label for="cpassword" class="mb-1">Confirm Password:</label>
        <input type="password" id="cpassword" bind:value={cpassword} class="border rounded px-3 py-2 w-full focus:outline-none focus:ring-2 focus:ring-blue-500" required />
      </div>

      <button type="submit" class="bg-red-800 text-white px-4 py-2 rounded focus:outline-none focus:ring-2 focus:ring-blue-500 focus:ring-offset-2">Register</button>
    </form>
  </div>
</main>

  