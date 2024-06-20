<script lang="ts">
    export let todo: string;
</script>

<div class="p-2 bg-slate-800 text-white flex gap-2">
    <input type="checkbox"/>
    <span>{todo}</span>
</div>