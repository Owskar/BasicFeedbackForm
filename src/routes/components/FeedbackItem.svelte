<script>
    import {createEventDispatcher} from 'svelte'
    import Card from "./Card.svelte";
    export let item

    const dispatch = createEventDispatcher()
const handleDelete = (itemId) =>{
dispatch('delete-feedback',itemId)
}




</script>

<Card>
    <div class="flex justify-between items-center mb-4">

        <div class="num-display bg-purple-600 text-white text-2xl font-bold w-12 h-12 rounded-full flex items-center justify-center -mt-10 -ml-6">
            {item.rating}
        </div>
 
        <button class="close text-gray-400 text-xl font-bold cursor-pointer hover:text-red-600 transition duration-200 ease-in-out" on:click={()=>handleDelete(item.id)}>
            X
        </button>
    </div>

   
    <p class="text-display mt-2 text-gray-700 text-lg leading-relaxed">
        {item.text}
    </p>
</Card>
