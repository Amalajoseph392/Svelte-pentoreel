<script>
  import Nav from "../Nav.svelte";

</script>
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/tailwindcss/2.2.19/tailwind.min.css">
  <title>Contact Us</title>
</head>
<Nav/>

<body class="bg-gray-100">
  <div class="flex flex-col justify-center items-center min-h-screen">
    <h1 class="text-4xl font-bold text-red-800 mb-4">Contact Us</h1>
    <div class="bg-white shadow-md p-6 rounded-lg w-full md:w-1/2 lg:w-1/3">
      <form>
        <div class="mb-4">
          <label for="name" class="block text-gray-700 font-bold mb-2">Name:</label>
          <input type="text" id="name" name="name" placeholder="Your Name" required
            class="w-full px-4 py-2 border border-gray-400 rounded-lg focus:outline-none focus:border-blue-500">
        </div>
        <div class="mb-4">
          <label for="email" class="block text-gray-700 font-bold mb-2">Email:</label>
          <input type="email" id="email" name="email" placeholder="Your Email" required
            class="w-full px-4 py-2 border border-gray-400 rounded-lg focus:outline-none focus:border-blue-500">
        </div>
        <div class="mb-4">
          <label for="message" class="block text-gray-700 font-bold mb-2">Message:</label>
          <textarea id="message" name="message" rows="4" placeholder="Your Message" required
            class="w-full px-4 py-2 border border-gray-400 rounded-lg focus:outline-none focus:border-blue-500"></textarea>
        </div>
        <div class="flex justify-center">
          <button type="submit"
            class="bg-red-800 hover:bg-red-800 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline">
            Send Message
          </button>
        </div>
      </form>
    </div>
  </div>
</body>

</html>
