<script>
    import Propeado from './Propeado.svelte'

    const helloWorld = 'Hello Im Nested!!'
    let count = 2
    $: helloWorldAndNumber = helloWorld + count
    $: if(count > 9) {
        alert('Count is high')
        count = 9
    }
    $: propeadoNumber = count * 4
    $: double = {
        number: count * 2
    }
</script>

<Propeado {...double} />
<Propeado number={propeadoNumber} />
<Propeado />

<p>{helloWorld}</p>
<button on:click={() => count++}>
    {count}
</button>
<p>HelloWorld + Count = {helloWorldAndNumber}</p>