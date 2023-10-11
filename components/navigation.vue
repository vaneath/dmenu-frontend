<template>
  <nav>
    <ul class="flex justify-evenly px-24">
      <li>
        <nuxt-link to="/">
          <img width="100" src="images/dmenu-logo.png" alt="Logo" />
        </nuxt-link>
      </li>
      <ul class="flex flex-1 justify-evenly items-center">
        <nav-link class="font-medium" to="/" title="Home" />
        <nav-link to="/about" title="About" />
        <nav-link to="/price" title="Price" />
        <nav-link to="/contact" title="Contact" />
      </ul>
      <ul class="flex items-center space-x-5">
        <nav-link to="/login" title="Login" type="button" />
      </ul>
    </ul>
  </nav>
</template>
