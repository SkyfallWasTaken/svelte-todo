<script lang="ts">
	export let todo: string;
</script>

<div class="flex gap-2 rounded-md bg-gray-600 p-2 text-white shadow-sm">
	<input type="checkbox" class="bg-gray-400" />
	<span>{todo}</span>
</div>
