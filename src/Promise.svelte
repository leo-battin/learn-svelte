<script>
    let promise;

    function handleInputChange(event) {
        promise = fetchData(event.target.value);
    }

    async function fetchData(string) {
        const response = await fetch('https://demo.dataverse.org/api/search?q=' + string);
        if (!response.ok) {
            throw new Error('Network response was not ok');
        }
        const data = await response.json();
        return data.data.items[0] ? data.data.items[0].name : null;
    }
</script>

<input type="text" on:input={handleInputChange}>
{#await promise}
    <p>...waiting</p>
{:then result}
    <p>{result ? result : 'no result...'}</p>
{/await}
