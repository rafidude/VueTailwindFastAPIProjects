<script>
    let question = "Am I Aware?"
    let frameworks = [
        {name: 'Vue', votes: 1},
        {name: 'React', votes: 1},
        {name: 'Angular', votes: 0},
        {name: 'Other', votes: 2},
    ]

    $: totalVotes = frameworks.reduce((sum, curr) => {
        return sum + curr.votes
    }, 0)

    const addVote = (name) => {
        frameworks = frameworks.map((fw) => {
            if (fw.name === name) {
                fw.votes++
                return fw
            }
            return fw
        })
    }
</script>

<main>
    <div class="px-40 py-20 flex">
        <div class="w-full shadow-md bg-gray-50 p-8">
            <p class="font-bold">{question}</p>
            {#each frameworks as fw}
                <div class="flex">
                    <p class="mr-4">{fw.name}</p>
                    <p class="font-bold">{totalVotes === 0 ? 0: fw.votes * 100/totalVotes }</p>
                    <button on:click={() => {addVote(fw.name)}}>Vote</button>
                </div>
            {/each}
        </div>
    </div>
</main>
