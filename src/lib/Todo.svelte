<script lang="ts">
	export let todo: string;
</script>

<div class="flex gap-2 bg-gray-600 p-2 rounded-md shadow-sm text-white">
	<input type="checkbox" class="bg-gray-400" />
	<span>{todo}</span>
</div>
