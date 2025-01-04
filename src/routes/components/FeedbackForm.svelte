<script>
    import Card from "./Card.svelte";
    import Button from "./Button.svelte";
    let text = ''
    let btnDisabled = false;
    let min = 10
    let message
    const handleInput = () => {
        if(text.trim().length<=min){
            message=`The text must be at list ${min} characters`
            btnDisabled =true
        }
        else{
            message= null
            btnDisabled = false
        }
    }
</script>

<Card>
    <header class="mb-6">
        <h2 class="text-xl font-bold text-gray-800">
            How would you rate your service with us?
        </h2>
    </header>
    <form class="space-y-4">
        <div class="input-group flex items-center gap-4">
            <input 
                type="text" 
                on:input={handleInput}
                bind:value={text} 
                placeholder="Enter your feedback"
                class="flex-1 px-4 py-2 text-gray-700 bg-gray-100 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-purple-500 focus:border-transparent placeholder-gray-500"
            />
            <Button 
                disabled={btnDisabled} 
                type="submit"
                class="px-6 py-2 text-white bg-purple-600 rounded-lg disabled:bg-gray-300 disabled:cursor-not-allowed hover:bg-purple-700 transition-all duration-200 ease-in-out">
                Send
            </Button>

            </div>
            {#if message}
            <div class="message">{message}</div>
            {/if}
    </form>
</Card>
