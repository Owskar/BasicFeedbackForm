<script>
    export let style = 'primary';
    export let type = 'button';
    export let disabled = false; 
</script>

<button 
    type={type} 
    disabled={disabled} 
    class={`px-6 py-2 text-lg font-semibold rounded-lg shadow-md transition duration-200 ease-in-out
        ${style === 'primary' ? 'bg-blue-500 text-white hover:bg-blue-600 disabled:bg-gray-300 disabled:cursor-not-allowed' : ''}
        ${style === 'secondary' ? 'bg-gray-200 text-gray-800 hover:bg-gray-300 disabled:bg-gray-300 disabled:cursor-not-allowed' : ''}
        ${style === 'danger' ? 'bg-red-500 text-white hover:bg-red-600 disabled:bg-gray-300 disabled:cursor-not-allowed' : ''}`}
>
    <slot></slot>
</button>
