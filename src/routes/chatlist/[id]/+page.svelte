<script lang="ts">
	import ChatPage from "../../../components/ChatPage.svelte";
	export let data: { id: string };
</script>
<ChatPage id={data.id} />
