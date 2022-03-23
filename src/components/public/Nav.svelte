<script>
	import LinkNav from './LinkNav.svelte';
	import ButtonNav from './ButtonNav.svelte';
	import Hamburger from './Hamburger.svelte';
	export let navbar = false;

  </script>

<nav class="bg-white border-gray-200 xs:px-0 sm:px-4 py-2.5 rounded dark:bg-gray-800">
	<div
		class="md:container xs:px-3 md:px-0 sm:px-0 flex flex-wrap justify-between items-center mx-auto"
	>
		<a href="/" class="flex items-center">
			<img src="/logo.svg" class="mr-3 h-10" alt="UACAK Logo" />
			<span
				class="xs:invisible sm:visible  self-center text-xl font-semibold whitespace-nowrap dark:text-white"
				>UACAK</span
			>
		</a>
		<div class="flex md:order-2">
			<ButtonNav text="Login" icon="<i class='ri-arrow-right-line ml-2'></i>" action="" />
			<Hamburger bind:open={navbar} />
		</div>
		<div
			class="{(navbar == false)?"hidden":""} justify-between items-center w-full md:flex md:w-auto md:order-1"
		>
			<ul
				class="flex flex-col mt-4 md:flex-row md:space-x-8 md:mt-0 md:text-sm md:font-medium"
			>
				<li>
					<LinkNav text="JOBS" link="/jobs" />
				</li>
				<li>
					<LinkNav text="COMPANIES" link="/companies" />
				</li>
				<li>
					<LinkNav text="BLOG" link="/blog" />
				</li>
				<li>
					<LinkNav text="CONTACT" link="/contact" />
				</li>
			</ul>
		</div>
	</div>
</nav>
