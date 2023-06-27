<script>
  let links = {
    'About': 'about',
    'Legal': 'legal',
    'Contact': 'contact'
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
  <div class="flex flex-col items-center md:pt-48 pt-24">
    <div class="flex flex-col items-center gap-6">
      <div class="flex flex-col md:flex-row items-center md:gap-8 gap-0">
        <p class="sm:text-9xl text-8xl font-extrabold text-slate-800">Luca</p>
        <p class="sm:text-9xl text-8xl font-extrabold text-slate-800">Krüger</p>
      </div>
      <div>
        <p class="sm:text-5xl text-4xl font-extrabold text-slate-800">Web Developer</p>
      </div>
      <div class="flex flex-col md:flex-row gap-4 pt-8">
        <a class="shadow-lg bg-slate-900 hover:opacity-90 transition ease-in duration-150 w-64 md:w-40 h-16 md:h-11 grid place-items-center rounded-lg" href="about">
          <p class="text-2xl md:text-base text-gray-50 font-semibold">About</p>
        </a>
        <a class="shadow-lg border border-gray-300 bg-gray-100 hover:bg-slate-900 hover:text-slate-50 hover:border-slate-900 text-slate-800 transition ease-in duration-150 w-64 md:w-40 h-16 md:h-11 grid place-items-center rounded-lg" href="services">
          <p class="text-2xl md:text-base font-semibold">Services</p>
        </a>
      </div>
    </div>
    <div class="flex flex-row items-center fixed bottom-2 gap-2">
      {#each getLinks() as link}
        <div>
          <a class="md:text-base text-xl font-semibold opacity-100 hover:opacity-75 transition ease-in duration-150 text-slate-800" href="{link.link}">{link.name}</a>
        </div>
        {#if !link.last}
          <p class="md:text-base text-xl font-semibold text-slate-800">|</p>
        {/if}
      {/each}
    </div>
  </div>
</main>

<style>
  a {
    text-decoration: none;
    color: black;
  }
</style>
