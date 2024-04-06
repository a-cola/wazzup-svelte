<script lang="ts">
    import { goto } from "$app/navigation";
</script>

<div class="error-page">
    <h1>Page Not Found</h1>
    <button class="home-button" onclick={()=>goto("/")}>Return to Start Page</button>
</div>