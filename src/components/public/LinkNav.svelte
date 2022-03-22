<script>
	export let text = '';
	export let link = '';
	import { page } from '$app/stores';
</script>

<a
	href={link}
	class="block py-2 pr-4 pl-3 {$page.url.pathname == link
		? 'text-white bg-blue-700 rounded md:bg-transparent md:text-blue-700 md:p-0 dark:text-white'
		: 'text-gray-700 border-b border-gray-100 hover:bg-gray-50 md:hover:bg-transparent md:border-0 md:hover:text-blue-700 md:p-0 md:dark:hover:text-white dark:text-gray-400 dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent dark:border-gray-700'}"
	>{text}
</a>
