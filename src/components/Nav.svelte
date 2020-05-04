<script>
  export let segment;
  
  let smallScreen = true
  let open = false
  let invert = false

  function toggleMenu() {
    open = !open
    invert = !invert
  }

</script>

<style>  
  header {
    display: flex;
    width: 90%;
    margin: auto;
    align-items: center;
    height: 10vh;
    position: relative;
  }
  .logo-container {
    /* background: lightblue; */
    flex: 1;
  }
  .logo {
    font-weight: 400;
    margin: 5px;
  }
  .logo-container,
  .nav-links,
  .cart {
    display: flex;
  }
  nav {
    /* background: rgba(189, 230, 173); */
    flex: 2;
  }
  .nav-links {
    justify-content: space-around;
    list-style: none;
    /* width: 50%; */
  }
  .logo-section,
  .nav-link {
    text-decoration: none;
    color: #5f5f79;
    font-size: 18px;
  }
  .cart {
    /* background: rgba(156, 37, 21); */
    flex: 1;
    justify-content: flex-end;
  }
  @media (max-width: 575px) {
    .line {
      width: 30px;
      height: 3px;
      /* background: #5f5f79; */
      background: #c36cbb;
      margin: 5px;
    }
    .hamburger {
      position: absolute;
      cursor: pointer;
      right: 0;
      top: 20px;
      z-index: 2;
    }
    header {
      flex-direction: column;
    }
    .nav-links {
      height: 100vh;
      width: 100vw;
      background: #5F5F79;      
      flex-direction: column;
       clip-path: circle(100px at 90% -20%);
      -webkit-clip-path: circle(100px at 90% -20%);
      transition: all 0.5s ease-out;
      pointer-events: none;
    }
    .open {
       clip-path: circle(1000px at 90% -20%);
      -webkit-clip-path: circle(1000px at 90% -20%);
      pointer-events: all;
    }
    .invert {
      /* background: white; */
      background: #c36cbb;
    }
    .logo-section,
    .cart {
      display: none;
    }
    .nav-links li {
      display: flex;
      justify-content: center;
      align-items: center;
    }
    .nav-links li a {
      color: white;
      z-index: 2;
    }

  }
</style>

<header>  
  <div class="hamburger" on:click={toggleMenu}>
    <div class="line" class:invert></div>
    <div class="line" class:invert></div>
    <div class="line" class:invert></div>
  </div>
  <a class="logo-section" aria-current={segment === 'undefined' ? 'page' : undefined} href=".">
    <div class="logo-container">
      <img src="/img/logo.svg" alt="" />
      <h4 class="logo">Three Dots</h4>
    </div>
  </a>
  <nav>
    <ul class="nav-links" class:open>
      <li>
        <a
          aria-current={segment === 'specs' ? 'page' : undefined}
          class="nav-link"
          href="specs">
          Specs
        </a>
      </li>
      <li>
        <a
          aria-current={segment === 'products' ? 'page' : undefined}
          class="nav-link"
          href="products">
          Products
        </a>
      </li>
      <li>
        <a
          aria-current={segment === 'contact' ? 'page' : undefined}
          class="nav-link"
          href="contact">
          Contact
        </a>
      </li>
    </ul>
  </nav>
    <div class="cart">
      <img src="/img/cart.svg" alt="" />
    </div>
</header>
