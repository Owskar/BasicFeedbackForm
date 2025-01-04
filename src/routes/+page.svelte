
<script>
//   import { text } from "@sveltejs/kit";
  import FeedbackForm from './components/FeedbackForm.svelte';
  import FeedbackList from  './components/FeedbackList.svelte'
  import FeedbackStats from './components/FeedbackStats.svelte';


    let feedback =[

    {
        id:1,
        rating:10,
        text : 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Pariatur veniam deserunt aliquam repellat. Iste debitis enim, quam repudiandae sunt, odit labore nostrum sed quis molestiae fugit cum consectetur inventore sint.'
    },
    {
        id:2,
        rating:9,
        text : 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Pariatur veniam deserunt aliquam repellat. Iste debitis enim, quam repudiandae sunt, odit labore nostrum sed quis molestiae fugit cum consectetur inventore sint.'
    },
    {
        id:3,
        rating:8,
        text : 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Pariatur veniam deserunt aliquam repellat. Iste debitis enim, quam repudiandae sunt, odit labore nostrum sed quis molestiae fugit cum consectetur inventore sint.'
    }
    ]

    $:count =feedback.length

    $:average = feedback.reduce((a,{rating})=> a+rating,0)/feedback.length

    const deleteFeedback =(e)=>{
        const itemId = e.detail
        feedback = feedback.filter((item)=>item.id!=itemId)
    }
</script>

<main>
    <FeedbackForm/>
    <FeedbackStats {count} {average}/>
<FeedbackList {feedback} on:delete-feedback={deleteFeedback}/>

</main>