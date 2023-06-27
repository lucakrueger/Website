<script>
    import Home from './Home.svelte'
    import About from './About.svelte'
    import Notfound from './Notfound.svelte'

    let RouterOutlet = Notfound

    let routes = {
        '/': Home,
        '/about': About
    }

    const GetRoute = () => {
        if(routes[window.location.pathname] === undefined) return Notfound

        return routes[window.location.pathname]
    }

    RouterOutlet = GetRoute()
</script>
<main>
    <svelte:component this={RouterOutlet} />
</main>