<script>
    import "../app.css";
</script>
<!-- 

<nav>
    <img src="https://www.alegsoftware.ga/immagini/logo_small.png" alt="..."/>
    <a href="/">Home</a>
    <a href="/about">About</a>
    <a href="/todo">To-do Test</a>
</nav> -->

<nav class="p-3 border-gray-200 rounded bg-gray-50">
    <div class="container flex flex-wrap items-center justify-between mx-auto">
      <a href="/" class="flex items-center">
          <img src="https://www.alegsoftware.ga/immagini/logo_small.png" class="h-6 mr-3 sm:h-10" alt="Flowbite Logo" />
      </a>
      
      <div class=" w-full md:block md:w-auto" id="navbar-solid-bg">
        <ul class="flex flex-col mt-4 rounded-lg bg-gray-50 md:flex-row md:space-x-8 md:mt-0 md:text-sm md:font-medium md:border-0 md:bg-transparent">

          <li>
            <a href="/" class="block py-2 pl-3 pr-4 text-gray-700 rounded hover:bg-gray-100 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 md:p-0 ">Home</a>
          </li>
          <li>
            <a href="/todo" class="block py-2 pl-3 pr-4 text-gray-700 rounded hover:bg-gray-100 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 md:p-0 ">To-do</a>
          </li>
          <li>
            <a href="/about" class="block py-2 pl-3 pr-4 text-gray-700 rounded hover:bg-gray-100 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 md:p-0 ">About</a>
          </li>
        </ul>
      </div>
    </div>
  </nav>




<slot>

</slot>