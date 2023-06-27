<script>
  let links = {
    'About': 'about.luca-krueger.com',
    'Legal': 'legal.luca-krueger.com',
    'Contact': 'contact.luca-krueger.com'
  }

  const getLinks = () => {
    let arr = []
    for(let key of Object.keys(links)) {
      arr.push({
        name: key,
        link: links[key],
        last: false
      })
    }
    arr[arr.length - 1].last = true

    return arr
  }
</script>

<main>
  <div class="vcontainer w-full h-3-4">
    <div class="vcontainer">
      <div class="title">
        <p class="cl-dark">Luca Krüger</p>
      </div>
      <div class="subtitle">
        <p class="cl-medium">Web Developer</p>
      </div>
    </div>
    <div class="scontainer hcontainer md-gap">
      {#each getLinks() as link}
        <div class="link">
          <a class="cl-dark" href="{link.link}">{link.name}</a>
        </div>
        {#if !link.last}
          <p class="vdivider cl-dark">|</p>
        {/if}
      {/each}
    </div>
  </div>
</main>

<style>
  .w-full {
    width: 100%;
  }

  .h-3-4 {
    height: 75%;
  }

  .vcontainer {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
  }

  .hcontainer {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: row;
  }

  .scontainer {
    position: fixed;
    bottom: 1rem
  }

  .vcontainer div {
    padding: 0;
    margin: 0;
  }

  .vcontainer div p {
    margin: 0
  }

  .title {
    /* font-size: 2.5rem; */
    font-size: 8rem;
    font-weight: 800;
  }

  .subtitle {
    /* font-size: 1.5rem; */
    font-size: 3rem;
    font-weight: 800;
  }

  .cl-dark {
    color: rgb(30 41 59);
  }

  .cl-medium {
    color: rgb(51 65 85);
  }

  .cl-light {
    color: rgb(148 163 184);
  }

  .sm-gap {
    gap: 0.2rem;
  }

  .md-gap {
    gap: 0.4rem;
  }

  .scontainer .social {
    width: 2rem;
    height: 2rem;
    background-color: black;
    border-radius: 50%;
  }

  a {
    text-decoration: none;
    color: black;
  }

  .link {
    font-size: 1rem;
    padding: 0.3rem;
    font-weight: 600;
  }

  .link:hover {
    opacity: 70%;
    cursor: pointer;
    transition: 0.2s;
    -webkit-transition: 0.2s;
  }

  .vdivider {
    cursor: default
  }
</style>
