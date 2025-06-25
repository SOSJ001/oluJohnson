<script>
	import { ToolIcon } from "svelte-feather-icons";

</script>
<div class="flex items-center justify-start mb-4 text-gray-100">
    <span class="rounded-full bg-purple-600 p-1">
        <!-- Default icon if none is provided -->
        <slot name="icon"> <ToolIcon /> </slot>
        
    </span>
  </div>