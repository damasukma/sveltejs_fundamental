<script>
    import Route from './Route.svelte'
    import Link from './Link.svelte'
    import { curRoute } from './store'

    const handlerBackNavigation = event => {
        curRoute.set('/')
        console.log(`Data ${JSON.stringify(event.state)}`)
    }
</script>



<style>
</style>
<svelte:window on:popstate={handlerBackNavigation}/>

<Link page={{ path: '/', name: 'Home' }}/>
<Link page={{ path: '/about', name: 'About' }}/>

<Route/>