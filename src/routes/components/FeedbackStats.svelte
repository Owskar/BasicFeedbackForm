<script>
    export let count
    export let average 
</script>

<div class="feedback-stats flex justify-between items-center">
    <h4 class="text-lg font-semibold text-gray-800 ml-5">
        {count} Reviews
    </h4>
    <h4 class="text-lg font-semibold text-gray-800 mr-5">
        Rating Average: {average}
    </h4>
</div>
