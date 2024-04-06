<script lang="ts">
    import {db} from '../db.svelte'
	import Message from './Message.svelte';

    const {id}:{id:string} = $props();
</script>

<div class="opened-chat">
    {#each db.getMessages(id) as msg}
        <Message 
            type={msg.sender}
            name={id}
            label={msg.text}
            time={msg.time}
        />
    {/each}
</div>