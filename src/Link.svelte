<script>
    import { curRoute } from './store'
    
    export let page;


    const redirectTo = event => {
        curRoute.set(event.target.pathname)

        window.history.pushState({path: page.path}, '', window.location.origin + page.path)
    }

</script>


<style>
a {
  text-transform: uppercase;
  text-decoration: underline;
  padding: 1rem;
}
</style>

<a href={page.path} on:click|preventDefault={redirectTo}>{page.name}</a>