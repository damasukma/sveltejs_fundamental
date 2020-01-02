<script>

import { onDestroy, onMount } from 'svelte'
import Todo from './../Todo.svelte'


onMount(() => console.log(history.state))
onDestroy(() => console.log("Hello"))

</script>

<style></style>
<main>
    <Todo url="https://jsonplaceholder.typicode.com/posts"/>
</main>