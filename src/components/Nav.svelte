<script>
  export let segment;
</script>

<style>
  nav {
    border-bottom: 1px solid rgba(255,62,0,0.1);
  }

  ul {
    margin: 0;
    padding: 0;
  }

  /* clearfix */

  [aria-current] {
    position: relative;
    display: inline-block;
  }

  [aria-current]::after {
    position: absolute;
    content: '';
    width: calc(100% - 1em);
    height: 2px;
    background-color: black;
    display: block;
    bottom: -1px;
  }

  a {
    padding: 0.5em 0.5em;
  }
</style>

<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <a class="navbar-brand" href='.'>Mood Tracker</a>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarToggler" aria-controls="navbarToggler" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>

  <div class="collapse navbar-collapse" id="navbarToggler">
    <ul class="navbar-nav mr-auto">
      <li class="nav-item"><a class="nav-link" aria-current='{segment === undefined ? "page" : undefined}' href='.'>home</a></li>
      <li class="nav-item"><a class="nav-link" rel=prefetch aria-current='{segment === "entries" ? "page" : undefined}' href='entries'>entries</a></li>
      <li class="nav-item"><a class="nav-link" aria-current='{segment === "about" ? "page" : undefined}' href='about'>about</a></li>
      <li class="nav-item"><a class="nav-link" rel=prefetch aria-current='{segment === "blog" ? "page" : undefined}' href='blog'>blog</a></li>
    </ul>
  </div>
</nav>
