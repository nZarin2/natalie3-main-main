

<script> import '../style.css'
let todoItem = '';
let todoList = [];
function addToArray() {
     if(todoItem==''){
          return;
     }
     todoList = [ ...todoList,{
          text: todoItem,
          done: false
     }]
     console.log(todoList);
     todoItem = '';
}
function removeThis(index){
     todoList.splice(index,1);
}
</script>
<h1>To do</h1>
<form on:submit={addToArray}>
     <input type="text" bind:value={todoItem}>
<button> submit </button>
</form>
<ul>
     {#each todoList as item, index}
 <li>
<input type="checkbox" bind:checked={item.done}>
<span class.done={item.done}>{item.text}</span>
     <span on:click={() => removeThis(index)}
          class="remove" role="button" tabindex="0">&items;
          {#if item.done}
          <button type="button" >Delete</button>
          {:else}
          <button type="button" >Edit</button>
          {/if}
          <button type="button" >Save</button>
</span>
</li>

{/each}
</ul>
<style>
     ul{
          list-style: none;
     }
     .done{
          color:aquamarine;
          text-decoration: line-through;
     }
     .remove{
          color:rgb(113, 6, 58);
     }

</style>
<div style =" margin:20; padding 400px:width:700px;">
     <h2 style="text align center">New list</h2>
     <input type="text">
     <button style="width:100px;">Add</button>
</div>
   