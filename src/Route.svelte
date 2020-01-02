<script>
    import { onDestroy, onMount } from 'svelte'
    import { curRoute } from './store'
    import router from './router'

    let component;

    const unsubscribe = curRoute.subscribe(value => {
        component = router.filter(r => r.path === $curRoute)[0].component;
    })


    onMount(() => {
        curRoute.set(window.location.pathname);
        if (!history.state) {
            window.history.replaceState({path: window.location.pathname}, '',   window.location.href)
        }
    })

    onDestroy(unsubscribe);

</script>


<style>
</style>

<div class="main-container">
   
    <svelte:component this={component}/>
</div>