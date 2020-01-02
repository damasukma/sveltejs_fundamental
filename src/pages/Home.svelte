<script>
    import { onDestroy, onMount } from 'svelte'
    
    let seconds = 0

    const time =  setInterval(() => seconds = seconds + 1, 1000)

    onMount(() => console.log(history.state))

    onDestroy(() => clearInterval(time))
</script>

<style>
    h2{
        color: coral;
    }
</style>

<h2>Time { seconds }</h2>