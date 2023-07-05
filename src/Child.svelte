<script>
    export let name = 'Hooman';
    export let arr;

    $: appended = [...arr, 'OY!']

    const createString = arr => {
        let string = '';
        arr.forEach(num => {
           string += num + ', '; 
        });
        return string.slice(0, -2);
    }
</script>

<p>Hello, {name}! Did you notice styles don't get applied to this nested component? appended is {createString(appended)}</p>
