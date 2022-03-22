<script>
	import Nav from '../../components/public/Nav.svelte';
	import Input from '../../components/public/Input.svelte';
	import Button from '../../components/public/Button.svelte';
</script>

<div class="container mx-auto px-10 mt-5 xs:mt-0 xs:mx-auto md:mt-5 md:mx-auto">
	<Nav />
	<hr />
	<div class="sm:grid sm:grid-flow-row sm:gap-3 xs:grid xs:grid-flow-row xs:gap-3 md:flex md:flex-row px-4 mt-6">
		<div class="basis-2/4 md:mr-2">
			<Input icon='<i class="ri-search-line"></i>' placeholder='Search jobs' />
		</div>
		<div class="basis-2/4 flex flex-row md:ml-2">
			<div class="basis-[100%] mr-1">
				<Input icon='<i class="ri-map-pin-2-line"></i>' placeholder='Location jobs (city)' />
			</div>
			<div class="basis-[12%] ml-1">
				<Button text="Search" icon="" action="" />
			</div>
		</div>
	</div>
</div>
