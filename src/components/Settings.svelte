<script lang="ts">
    import SettingsIcon from "./SettingsIcon.svelte";

    let {sv = $bindable()}:{sv:'none'|'flex'} = $props();

    const settings:string[]=["Generale", "Account", "Chat", "Video e audio", "Notifiche", "Personalizzazione", "Archiviazione", "Collegamenti rapidi", "Aiuto", "Profilo"];
</script>

<div class="settings-modal" style:display={sv}>
    <div class="settings">
        <div class="close-settings">
            <button onclick={() => sv = 'none'}>&times;</button>
        </div>
        {#each settings as setting}
            <div class="setting-line">
                <SettingsIcon label={setting}/>
                <span>{setting}</span>
            </div>
        {/each}
    </div>
</div>