<script lang="ts" >
    import {onMount} from 'svelte'
      export let color :string = "cyan" || "samon" || "goldenrod"
      export let id: string
     let wrapper
     
      let queryString = "#"+id
     
      
onMount( () => {
  let stuff = document.querySelector(queryString)
    stuff.classList.add(color)
   console.log(id, stuff, color);
  })
   
   
   
      
</script>


<div bind:this="{wrapper}" {id} class="container {color}"  {color}>
<slot/>

</div>


<style>
.container {
    margin: 1em;
    /* background-color: blue; */
    width: 300px;
    height: 300px;

}

.cyan {background-color: cyan;}
.salmon {background-color: salmon;}
.goldenrod {background-color: goldenrod;}


</style>