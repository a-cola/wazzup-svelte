<script lang="ts">
	import { goto } from "$app/navigation";
    import { db } from "../db.svelte";

    type chatSmallProps = {
        name: string,
        label: string,
        time: string,
        count: string,
        id: string,
    }

    let {name,label,time,count, id}:chatSmallProps = $props();
</script>

<button class="chat-small" onclick={()=>{db.resetChatCount(id); goto("/chatlist/"+id)}}>
    <div class="profile-pic">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512">
        <path d="M224 256A128 128 0 1 0 224 0a128 128 0 1 0 0 256zm-45.7 48C79.8 304 0 383.8 0 482.3C0 498.7 13.3 512 29.7 512H418.3c16.4 0 29.7-13.3 29.7-29.7C448 383.8 368.2 304 269.7 304H178.3z"/>
        </svg>
    </div>
    <div class="last-chat">
        <span>{name}</span>
        <span style="font-size: 10px; color: rgb(89, 89, 89);">{label}</span>
    </div>
    <div class="info">
        <span class="time">{time}</span>
        {#if count!=='0'}
            <span class="notify-count">{count}</span>
        {/if}
    </div>
</button>