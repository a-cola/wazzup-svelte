<script lang="ts">
    import {db} from "../db.svelte"

    type msgPropType = {
        type: string,
        name: string,
        label: string,
        time: string,
    }
    let {type, name, label, time}:msgPropType = $props();
</script>

<div class={type==='sent'?'sent':'received'}>
    <div class={type==='sent'?'text-box-s':'text-box-r'}>
        {#if (db.isGroup(name)&&type!=='sent')}
            <span class="name">{type}</span>
        {/if}
        <span>{label}</span>
        <span class="chat-time" style="color:gray;">{time}</span>
    </div>
</div>