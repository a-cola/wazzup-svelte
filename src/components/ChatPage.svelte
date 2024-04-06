<script lang="ts">
    import ChatList from "./ChatList.svelte";
    import CurrentChat from "./CurrentChat.svelte";
    
    let {id}:{id:string} = $props();
</script>

<div class="container">
    <ChatList />
    <CurrentChat id={id}/>
</div>