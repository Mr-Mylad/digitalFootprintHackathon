<script>
    import { marked } from "marked";
    marked.setOptions({ sanitize: true });
    let props = $props();
</script>
  
<div class="bg-blue-800 max-w-3xl w-fit border-2 border-black rounded-md p-2 self-end">
    <p class="text-white">{@html marked(props.message)}</p>
</div>
