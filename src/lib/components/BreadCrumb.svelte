<script>
	import { page } from "$app/state";

    let crumb = page.url.pathname

    
</script>
<div class="container mx-auto px-4 py-5">
	<nav aria-label="Breadcrumb">
		<ol class="list-reset flex">
			<li>
				<a href="/" class="text-gray-600 hover:text-purple-700">Olu Johnson</a>
			</li>
			<li class="mx-2 text-gray-600">›</li>
			<li>
				<span class="text-gray-600">{crumb}</span>
			</li>
		</ol>
	</nav>
</div>