<script>
	import Nav from '../../components/public/Nav.svelte';
	import Input from '../../components/public/Input.svelte';
	import Button from '../../components/public/Button.svelte';

	let accordion1 = true;
	let accordion2 = true;
	let accordion3 = true;
	let accordion4 = true;

	let filter = false;
</script>

<div class="xs:mt-0 xs:mx-auto lg:container lg:px-10 lg:mt-5 lg:mx-auto">
	<Nav />
	<hr />
	<div
		class="sm:grid sm:grid-flow-row sm:gap-3 xs:grid xs:grid-flow-row xs:gap-3 md:flex md:flex-row px-4 mt-6"
	>
		<div class="basis-2/4 md:mr-2">
			<Input icon="<i class='ri-search-line focus:blue-500'></i>" placeholder="Search jobs" />
		</div>
		<div class="basis-2/4 flex flex-row md:ml-2">
			<div class="basis-[100%] mr-1">
				<Input icon="<i class='ri-map-pin-2-line'></i>" placeholder="Location jobs (city)" />
			</div>
			<div class="basis-[12%] ml-1">
				<Button text="Search" icon="" action="" />
			</div>
		</div>
	</div>
	<div class="flex justify-center px-4">
		<button type="button" on:click="{()=>{filter = !filter}}" class="basis-4/4 w-full rounded-3xl items-center bg-transparent border-2 border-gray-300 text-slate-500 px-12 mt-3 md:hidden"><i class="ri-equalizer-fill"></i> Filter</button>
	</div>
	<div class="xs:grid sm:grid md:grid md:grid-cols-3 mt-6">
		<div class="{(filter == false)?"xs:hidden sm:hidden md:block":""} xs:px-4 sm:px-4  md:col-span-1">
			<div class="overflow-y-auto xs:max-h-[68vh] sm:max-h-[75vh] md:max-h-[78vh] border-2 border-gray-300 rounded-lg ">
				<div class="h-12 flex justify-between items-center pl-5 w-full font-medium text-left">
					<p class="font-semibold text-lg">Filter your search</p>
					<button class="text-xs mr-3 font-inter text-red-700">Reset</button>
				</div>
				<hr />

				<button
					on:click={() => {
						accordion1 == true ? (accordion1 = false) : (accordion1 = true);
					}}
					aria-expanded={accordion1}
					type="button"
					class="flex justify-between w-full px-4 py-4 rounded-t-lg text-gray-800 focus:bg-transparent bg-transparent"
				>
					<span class="items-center text-left font-semibold text-sm">Sort By</span>
					<svg
						data-accordion-icon
						class="items-center font-medium text-right w-6 h-6 {accordion1 == true
							? 'rotate-180'
							: ''} shrink-0"
						fill="currentColor"
						viewBox="0 0 20 20"
						xmlns="http://www.w3.org/2000/svg"
						><path
							fill-rule="evenodd"
							d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z"
							clip-rule="evenodd"
						/></svg
					>
				</button>

				{#if accordion1}
					<div>
						<div class="flex justify-center w-full pt-2 pb-4">
							<button
								type="button"
								class="py-1.5 px-4 mr-2 mb-2 text-sm font-medium text-slate-700 focus:outline-none bg-white rounded-full border border-gray-200 hover:bg-gray-100 hover:text-blue-700 focus:z-10 focus:ring-4 focus:ring-gray-200 dark:focus:ring-gray-700 dark:bg-gray-800 dark:text-gray-400 dark:border-gray-600 dark:hover:text-white dark:hover:bg-gray-700"
							>
								Relevancy
							</button>
							<button
								type="button"
								class="py-1.5 px-4 mr-2 mb-2 text-sm font-medium text-slate-700 focus:outline-none bg-white rounded-full border border-gray-200 hover:bg-gray-100 hover:text-blue-700 focus:z-10 focus:ring-4 focus:ring-gray-200 dark:focus:ring-gray-700 dark:bg-gray-800 dark:text-gray-400 dark:border-gray-600 dark:hover:text-white dark:hover:bg-gray-700"
							>
								Newest
							</button>
						</div>
						<hr />
					</div>
				{/if}

				<button
					on:click={() => {
						accordion2 == true ? (accordion2 = false) : (accordion2 = true);
					}}
					type="button"
					class="flex justify-between w-full px-4 py-4 rounded-t-lg text-gray-800 focus:bg-transparent bg-transparent"
				>
					<span class="items-center text-left font-semibold text-sm">Job Type</span>
					<svg
						data-accordion-icon
						class="items-center font-medium text-right w-6 h-6 {accordion2 == true
							? 'rotate-180'
							: ''} shrink-0"
						fill="currentColor"
						viewBox="0 0 20 20"
						xmlns="http://www.w3.org/2000/svg"
						><path
							fill-rule="evenodd"
							d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z"
							clip-rule="evenodd"
						/></svg
					>
				</button>
				{#if accordion2}
					<div>
						<div class="flex flex-col justify-start w-full pl-4 pb-4">
							<div class="flex items-center">
								<input
									id="checkbox-all-search1"
									type="checkbox"
									class="cursor-pointer w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 rounded	 focus:ring-offset-1 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-800 focus:ring-2 dark:bg-gray-700 dark:border-gray-600"
								/>
								<label for="checkbox-all-search1" class="ml-2 font-semibold text-slate-700"
									>Full-time</label
								>
							</div>
							<div class="flex items-center">
								<input
									id="checkbox-all-search2"
									type="checkbox"
									class="cursor-pointer w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 rounded	 focus:ring-offset-1 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-800 focus:ring-2 dark:bg-gray-700 dark:border-gray-600"
								/>
								<label for="checkbox-all-search2" class="ml-2 font-semibold text-slate-700"
									>Part-time</label
								>
							</div>
							<div class="flex items-center">
								<input
									id="checkbox-all-search3"
									type="checkbox"
									class="cursor-pointer w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 rounded	 focus:ring-offset-1 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-800 focus:ring-2 dark:bg-gray-700 dark:border-gray-600"
								/>
								<label for="checkbox-all-search3" class="ml-2 font-semibold text-slate-700"
									>Freelance</label
								>
							</div>
							<div class="flex items-center">
								<input
									id="checkbox-all-search4"
									type="checkbox"
									class="cursor-pointer w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 rounded	 focus:ring-offset-1 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-800 focus:ring-2 dark:bg-gray-700 dark:border-gray-600"
								/>
								<label for="checkbox-all-search4" class="ml-2 font-semibold text-slate-700"
									>Remote</label
								>
							</div>
						</div>
						<hr />
					</div>
				{/if}

				<button
					on:click={() => {
						accordion3 == true ? (accordion3 = false) : (accordion3 = true);
					}}
					type="button"
					class="flex justify-between w-full px-4 py-4 rounded-t-lg text-gray-800 focus:bg-transparent bg-transparent"
				>
					<span class="items-center text-left font-semibold text-sm">Experience</span>
					<svg
						data-accordion-icon
						class="items-center font-medium text-right w-6 h-6 {accordion3 == true
							? 'rotate-180'
							: ''} shrink-0"
						fill="currentColor"
						viewBox="0 0 20 20"
						xmlns="http://www.w3.org/2000/svg"
						><path
							fill-rule="evenodd"
							d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z"
							clip-rule="evenodd"
						/></svg
					>
				</button>
				{#if accordion3}
					<div>
						<div class="flex flex-col justify-start w-full pl-4 pb-4">
							<div class="flex items-center">
								<input
									id="experience1"
									type="checkbox"
									class="cursor-pointer w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 rounded	 focus:ring-offset-1 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-800 focus:ring-2 dark:bg-gray-700 dark:border-gray-600"
								/>
								<label for="experience1" class="ml-2 font-semibold text-slate-700"
									>Less than a year</label
								>
							</div>
							<div class="flex items-center">
								<input
									id="experience2"
									type="checkbox"
									class="cursor-pointer w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 rounded	 focus:ring-offset-1 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-800 focus:ring-2 dark:bg-gray-700 dark:border-gray-600"
								/>
								<label for="experience2" class="ml-2 font-semibold text-slate-700"
									>1 – 3 years</label
								>
							</div>
							<div class="flex items-center">
								<input
									id="experience3"
									type="checkbox"
									class="cursor-pointer w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 rounded	 focus:ring-offset-1 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-800 focus:ring-2 dark:bg-gray-700 dark:border-gray-600"
								/>
								<label for="experience3" class="ml-2 font-semibold text-slate-700"
									>3 – 5 years</label
								>
							</div>
							<div class="flex items-center">
								<input
									id="experience4"
									type="checkbox"
									class="cursor-pointer w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 rounded	 focus:ring-offset-1 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-800 focus:ring-2 dark:bg-gray-700 dark:border-gray-600"
								/>
								<label for="experience4" class="ml-2 font-semibold text-slate-700"
									>5 – 10 years</label
								>
							</div>
							<div class="flex items-center">
								<input
									id="experience5"
									type="checkbox"
									class="cursor-pointer w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 rounded	 focus:ring-offset-1 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-800 focus:ring-2 dark:bg-gray-700 dark:border-gray-600"
								/>
								<label for="experience5" class="ml-2 font-semibold text-slate-700"
									>More than 10 years</label
								>
							</div>
						</div>
						<hr />
					</div>
				{/if}

				<button
					on:click={() => {
						accordion4 == true ? (accordion4 = false) : (accordion4 = true);
					}}
					type="button"
					class="flex justify-between w-full px-4 py-4 rounded-t-lg text-gray-800 focus:bg-transparent bg-transparent"
				>
					<span class="items-center text-left font-semibold text-sm">Job Categories</span>
					<svg
						data-accordion-icon
						class="items-center font-medium text-right w-6 h-6 {accordion4 == true
							? 'rotate-180'
							: ''} shrink-0"
						fill="currentColor"
						viewBox="0 0 20 20"
						xmlns="http://www.w3.org/2000/svg"
						><path
							fill-rule="evenodd"
							d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z"
							clip-rule="evenodd"
						/></svg
					>
				</button>
				{#if accordion4}
					<div>
						<div class="px-4">
							<Input
								icon="<i class='ri-search-line'></i>"
								value="Delevoper"
								placeholder="Search categories"
							/>
						</div>
						<div class="px-4 my-2">
							<div class="grid grid-flow-row auto-rows-max gap-2">
								<div>
									<input
										id="jobcategories1"
										type="checkbox"
										class="cursor-pointer w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 rounded	 focus:ring-offset-1 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-800 focus:ring-2 dark:bg-gray-700 dark:border-gray-600"
									/>
									<label for="jobcategories1" class="ml-2 font-semibold text-slate-700"
										>Developer</label
									>
								</div>
								<div>
									<input
										id="jobcategories2"
										type="checkbox"
										class="cursor-pointer w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 rounded	 focus:ring-offset-1 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-800 focus:ring-2 dark:bg-gray-700 dark:border-gray-600"
									/>
									<label for="jobcategories2" class="ml-2 font-semibold text-slate-700">Admin</label
									>
								</div>
								<div>
									<input
										id="jobcategories3"
										type="checkbox"
										class="cursor-pointer w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 rounded	 focus:ring-offset-1 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-800 focus:ring-2 dark:bg-gray-700 dark:border-gray-600"
									/>
									<label for="jobcategories3" class="ml-2 font-semibold text-slate-700"
										>Writter</label
									>
								</div>
								<div>
									<input
										id="jobcategories4"
										type="checkbox"
										class="cursor-pointer w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 rounded	 focus:ring-offset-1 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-800 focus:ring-2 dark:bg-gray-700 dark:border-gray-600"
									/>
									<label for="jobcategories4" class="ml-2 font-semibold text-slate-700"
										>Desinger</label
									>
								</div>
								<div>
									<input
										id="jobcategories5"
										type="checkbox"
										checked
										class="cursor-pointer w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 rounded	 focus:ring-offset-1 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-800 focus:ring-2 dark:bg-gray-700 dark:border-gray-600"
									/>
									<label for="jobcategories5" class="ml-2 font-semibold text-slate-700"
										>Frontend Developer</label
									>
								</div>
								<div>
									<input
										id="jobcategories6"
										type="checkbox"
										checked
										class="cursor-pointer w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 rounded	 focus:ring-offset-1 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-800 focus:ring-2 dark:bg-gray-700 dark:border-gray-600"
									/>
									<label for="jobcategories6" class="ml-2 font-semibold text-slate-700"
										>Backend Developer</label
									>
								</div>
								<div>
									<input
										id="jobcategories7"
										type="checkbox"
										class="cursor-pointer w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 rounded	 focus:ring-offset-1 focus:ring-blue-500 dark:focus:ring-blue-600 dark:ring-offset-gray-800 focus:ring-2 dark:bg-gray-700 dark:border-gray-600"
									/>
									<label for="jobcategories7" class="ml-2 font-semibold text-slate-700">UI/UX</label
									>
								</div>
							</div>
						</div>
						<div class="px-4 my-2 gap-2">
							<ul class="text-xs">
								<li class="mt-2 flex justify-start items-center">
									- Backend Developer <i
										class="ml-2 bg-red-700 text-white rounded-sm p-0.5 ri-delete-bin-7-line hover:bg-red-800 cursor-pointer"
									/>
								</li>
								<li class="mt-2 flex justify-start items-center">
									- Frontend Developer <i
										class="ml-2 bg-red-700 text-white rounded-sm p-0.5 ri-delete-bin-7-line hover:bg-red-800 cursor-pointer"
									/>
								</li>
							</ul>
						</div>
						<hr />
					</div>
				{/if}
			</div>
		</div>
		<div class=" xs:px-4 sm:px-4 md:col-span-2">
			<div class="xs:flex xs:flex-col sm:flex sm:flex-col lg:grid lg:grid-cols-2 xs:gap-3 overflow-y-auto xs:max-h-[68vh] sm:max-h-[75vh] md:max-h-[78vh]">
				<div class="xs:basis-[100%] sm:basis-[100%] md:basis-[100%]">
					<div class=" rounded-lg border-2">
						<div class="grid grid-flow-row auto-rows-max m-3">
							<div class="flex justify-between">
								<div class="flex ">
									<div class="w-14 h-14 bg-slate-500 rounded-lg bg-cover" style="background-image: url(https://picsum.photos/200/300?random=1)"></div>
									<div class="ml-2">
										<p class="text-lg font-semibold">Banking Back Office</p>
										<a href="/" class="text-sm cursor-pointer hover:text-blue-500">PT. Mutualplus Global Resource</a>
									</div>
								</div>
								<i class="ri-bookmark-line ri-xl hover:text-blue-500 cursor-pointer"></i>
							</div>
							<div class="flex flex-row mt-2 items-center">
								<i class="ri-map-pin-2-fill ri-lg"></i> 
								<p class="font-semibold ml-1">Senen, Jakarta</p>
							</div>
							<div class="flex flex-row mt-2 items-center">
								<i class="ri-money-dollar-circle-line ri-lg"></i>
								<p class="ml-1 font-semibold text-sm">IDR 4.500.000 - 8.000.000</p>
							</div>
							<div class="flex flex-row mt-2 items-center">
								<i class="ri-briefcase-2-line"></i>
								<p class="ml-1 font-semibold text-sm">3 - 5 years</p>
							</div>
							<div class="flex flex-row mt-2 items-center">
								<button type="button" class="p-1 pr-2 text-xs bg-lime-600 rounded-xl text-white flex items-center"><i class="ri-calendar-line mr-1"></i> Actively Hiring</button>
								<i class="ri-time-line ri-md text-gray-400 ml-2"></i>
								<p class="ml-1 font-semibold text-sm text-gray-400">Created 1 month ago</p>
							</div>
						</div>
					</div>
				</div>
				<div class="xs:basis-[100%] sm:basis-[100%] md:basis-[100%]">
					<div class=" rounded-lg border-2">
						<div class="grid grid-flow-row auto-rows-max m-3">
							<div class="flex justify-between">
								<div class="flex ">
									<div class="w-14 h-14 bg-slate-500 rounded-lg bg-cover" style="background-image: url(https://picsum.photos/200/300?random=2)"></div>
									<div class="ml-2">
										<p class="text-lg font-semibold">Senior QA Engineer</p>
										<a href="/" class="text-sm cursor-pointer hover:text-blue-500">Dropsuite</a>
									</div>
								</div>
								<i class="ri-bookmark-line ri-xl hover:text-blue-500 cursor-pointer"></i>
							</div>
							<div class="flex flex-row mt-2 items-center">
								<i class="ri-map-pin-2-fill ri-lg"></i> 
								<p class="font-semibold ml-1">Bandung</p>
							</div>
							<div class="flex flex-row mt-2 items-center">
								<i class="ri-money-dollar-circle-line ri-lg"></i>
								<p class="ml-1 font-semibold text-sm">IDR 10.500.000 - 18.000.000</p>
							</div>
							<div class="flex flex-row mt-2 items-center">
								<i class="ri-briefcase-2-line"></i>
								<p class="ml-1 font-semibold text-sm">3 - 5 years</p>
							</div>
							<div class="flex flex-row mt-2 items-center">
								<button type="button" class="p-1 pr-2 text-xs bg-red-600 rounded-xl text-white flex items-center"><i class="ri-close-line mr-1"></i>Closed</button>
								<i class="ri-time-line ri-md text-gray-400 ml-2"></i>
								<p class="ml-1 font-semibold text-sm text-gray-400">Created 5 days ago</p>
							</div>
						</div>
					</div>
				</div>
				<div class="xs:basis-[100%] sm:basis-[100%] md:basis-[100%]">
					<div class=" rounded-lg border-2">
						<div class="grid grid-flow-row auto-rows-max m-3">
							<div class="flex justify-between">
								<div class="flex ">
									<div class="w-14 h-14 bg-slate-500 rounded-lg bg-cover" style="background-image: url(https://picsum.photos/200/300?random=3)"></div>
									<div class="ml-2">
										<p class="text-lg font-semibold">Senior QA Engineer</p>
										<a href="/" class="text-sm cursor-pointer hover:text-blue-500">Dropsuite</a>
									</div>
								</div>
								<i class="ri-bookmark-line ri-xl hover:text-blue-500 cursor-pointer"></i>
							</div>
							<div class="flex flex-row mt-2 items-center">
								<i class="ri-map-pin-2-fill ri-lg"></i> 
								<p class="font-semibold ml-1">Bandung</p>
							</div>
							<div class="flex flex-row mt-2 items-center">
								<i class="ri-money-dollar-circle-line ri-lg"></i>
								<p class="ml-1 font-semibold text-xs"><a href="/" class="text-blue-500 hover:text-blue-800">Login</a> to view salary by uacak</p>
							</div>
							<div class="flex flex-row mt-2 items-center">
								<i class="ri-briefcase-2-line"></i>
								<p class="ml-1 font-semibold text-sm">3 - 5 years</p>
							</div>
							<div class="flex flex-row mt-2 items-center">
								<button type="button" class="p-1 pr-2 text-xs bg-red-600 rounded-xl text-white flex items-center"><i class="ri-close-line mr-1"></i>Closed</button>
								<i class="ri-time-line ri-md text-gray-400 ml-2"></i>
								<p class="ml-1 font-semibold text-sm text-gray-400">Created 5 days ago</p>
							</div>
						</div>
					</div>
				</div>
				<div class="xs:basis-[100%] sm:basis-[100%] md:basis-[100%]">
					<div class=" rounded-lg border-2">
						<div class="grid grid-flow-row auto-rows-max m-3">
							<div class="flex justify-between">
								<div class="flex ">
									<div class="w-14 h-14 bg-slate-500 rounded-lg bg-cover" style="background-image: url(https://picsum.photos/200/300?random=4)"></div>
									<div class="ml-2">
										<p class="text-lg font-semibold">Senior QA Engineer</p>
										<a href="/" class="text-sm cursor-pointer hover:text-blue-500">Dropsuite</a>
									</div>
								</div>
								<i class="ri-bookmark-line ri-xl hover:text-blue-500 cursor-pointer"></i>
							</div>
							<div class="flex flex-row mt-2 items-center">
								<i class="ri-map-pin-2-fill ri-lg"></i> 
								<p class="font-semibold ml-1">Bandung</p>
							</div>
							<div class="flex flex-row mt-2 items-center">
								<i class="ri-money-dollar-circle-line ri-lg"></i>
								<p class="ml-1 font-semibold text-sm">IDR 10.500.000 - 18.000.000</p>
							</div>
							<div class="flex flex-row mt-2 items-center">
								<i class="ri-briefcase-2-line"></i>
								<p class="ml-1 font-semibold text-sm">3 - 5 years</p>
							</div>
							<div class="flex flex-row mt-2 items-center">
								<button type="button" class="p-1 pr-2 text-xs bg-red-600 rounded-xl text-white flex items-center"><i class="ri-close-line mr-1"></i>Closed</button>
								<i class="ri-time-line ri-md text-gray-400 ml-2"></i>
								<p class="ml-1 font-semibold text-sm text-gray-400">Created 5 days ago</p>
							</div>
						</div>
					</div>
				</div>
				<div class="xs:basis-[100%] sm:basis-[100%] md:basis-[100%]">
					<div class=" rounded-lg border-2">
						<div class="grid grid-flow-row auto-rows-max m-3">
							<div class="flex justify-between">
								<div class="flex ">
									<div class="w-14 h-14 bg-slate-500 rounded-lg bg-cover" style="background-image: url(https://picsum.photos/200/300?random=5)"></div>
									<div class="ml-2">
										<p class="text-lg font-semibold">Senior QA Engineer</p>
										<a href="/" class="text-sm cursor-pointer hover:text-blue-500">Dropsuite</a>
									</div>
								</div>
								<i class="ri-bookmark-line ri-xl hover:text-blue-500 cursor-pointer"></i>
							</div>
							<div class="flex flex-row mt-2 items-center">
								<i class="ri-map-pin-2-fill ri-lg"></i> 
								<p class="font-semibold ml-1">Bandung</p>
							</div>
							<div class="flex flex-row mt-2 items-center">
								<i class="ri-money-dollar-circle-line ri-lg"></i>
								<p class="ml-1 font-semibold text-sm">IDR 10.500.000 - 18.000.000</p>
							</div>
							<div class="flex flex-row mt-2 items-center">
								<i class="ri-briefcase-2-line"></i>
								<p class="ml-1 font-semibold text-sm">3 - 5 years</p>
							</div>
							<div class="flex flex-row mt-2 items-center">
								<button type="button" class="p-1 pr-2 text-xs bg-red-600 rounded-xl text-white flex items-center"><i class="ri-close-line mr-1"></i>Closed</button>
								<i class="ri-time-line ri-md text-gray-400 ml-2"></i>
								<p class="ml-1 font-semibold text-sm text-gray-400">Created 5 days ago</p>
							</div>
						</div>
					</div>
				</div>
				<div class="xs:basis-[100%] sm:basis-[100%] md:basis-[100%]">
					<div class=" rounded-lg border-2">
						<div class="grid grid-flow-row auto-rows-max m-3">
							<div class="flex justify-between">
								<div class="flex ">
									<div class="w-14 h-14 bg-slate-500 rounded-lg bg-cover" style="background-image: url(https://picsum.photos/200/300?random=5)"></div>
									<div class="ml-2">
										<p class="text-lg font-semibold">Senior QA Engineer</p>
										<a href="/" class="text-sm cursor-pointer hover:text-blue-500">Dropsuite</a>
									</div>
								</div>
								<i class="ri-bookmark-line ri-xl hover:text-blue-500 cursor-pointer"></i>
							</div>
							<div class="flex flex-row mt-2 items-center">
								<i class="ri-map-pin-2-fill ri-lg"></i> 
								<p class="font-semibold ml-1">Bandung</p>
							</div>
							<div class="flex flex-row mt-2 items-center">
								<i class="ri-money-dollar-circle-line ri-lg"></i>
								<p class="ml-1 font-semibold text-sm">IDR 10.500.000 - 18.000.000</p>
							</div>
							<div class="flex flex-row mt-2 items-center">
								<i class="ri-briefcase-2-line"></i>
								<p class="ml-1 font-semibold text-sm">3 - 5 years</p>
							</div>
							<div class="flex flex-row mt-2 items-center">
								<button type="button" class="p-1 pr-2 text-xs bg-red-600 rounded-xl text-white flex items-center"><i class="ri-close-line mr-1"></i>Closed</button>
								<i class="ri-time-line ri-md text-gray-400 ml-2"></i>
								<p class="ml-1 font-semibold text-sm text-gray-400">Created 5 days ago</p>
							</div>
						</div>
					</div>
				</div>
				<div class="xs:basis-[100%] sm:basis-[100%] md:basis-[100%]">
					<div class=" rounded-lg border-2">
						<div class="grid grid-flow-row auto-rows-max m-3">
							<div class="flex justify-between">
								<div class="flex ">
									<div class="w-14 h-14 bg-slate-500 rounded-lg bg-cover" style="background-image: url(https://picsum.photos/200/300?random=6)"></div>
									<div class="ml-2">
										<p class="text-lg font-semibold">Senior QA Engineer</p>
										<a href="/" class="text-sm cursor-pointer hover:text-blue-500">Dropsuite</a>
									</div>
								</div>
								<i class="ri-bookmark-line ri-xl hover:text-blue-500 cursor-pointer"></i>
							</div>
							<div class="flex flex-row mt-2 items-center">
								<i class="ri-map-pin-2-fill ri-lg"></i> 
								<p class="font-semibold ml-1">Bandung</p>
							</div>
							<div class="flex flex-row mt-2 items-center">
								<i class="ri-money-dollar-circle-line ri-lg"></i>
								<p class="ml-1 font-semibold text-sm">IDR 10.500.000 - 18.000.000</p>
							</div>
							<div class="flex flex-row mt-2 items-center">
								<i class="ri-briefcase-2-line"></i>
								<p class="ml-1 font-semibold text-sm">3 - 5 years</p>
							</div>
							<div class="flex flex-row mt-2 items-center">
								<button type="button" class="p-1 pr-2 text-xs bg-red-600 rounded-xl text-white flex items-center"><i class="ri-close-line mr-1"></i>Closed</button>
								<i class="ri-time-line ri-md text-gray-400 ml-2"></i>
								<p class="ml-1 font-semibold text-sm text-gray-400">Created 5 days ago</p>
							</div>
						</div>
					</div>
				</div>
				<div class="xs:basis-[100%] sm:basis-[100%] md:basis-[100%]">
					<div class=" rounded-lg border-2">
						<div class="grid grid-flow-row auto-rows-max m-3">
							<div class="flex justify-between">
								<div class="flex ">
									<div class="w-14 h-14 bg-slate-500 rounded-lg bg-cover" style="background-image: url(https://picsum.photos/200/300?random=7)"></div>
									<div class="ml-2">
										<p class="text-lg font-semibold">Senior QA Engineer</p>
										<a href="/" class="text-sm cursor-pointer hover:text-blue-500">Dropsuite</a>
									</div>
								</div>
								<i class="ri-bookmark-line ri-xl hover:text-blue-500 cursor-pointer"></i>
							</div>
							<div class="flex flex-row mt-2 items-center">
								<i class="ri-map-pin-2-fill ri-lg"></i> 
								<p class="font-semibold ml-1">Bandung</p>
							</div>
							<div class="flex flex-row mt-2 items-center">
								<i class="ri-money-dollar-circle-line ri-lg"></i>
								<p class="ml-1 font-semibold text-sm">IDR 10.500.000 - 18.000.000</p>
							</div>
							<div class="flex flex-row mt-2 items-center">
								<i class="ri-briefcase-2-line"></i>
								<p class="ml-1 font-semibold text-sm">3 - 5 years</p>
							</div>
							<div class="flex flex-row mt-2 items-center">
								<button type="button" class="p-1 pr-2 text-xs bg-red-600 rounded-xl text-white flex items-center"><i class="ri-close-line mr-1"></i>Closed</button>
								<i class="ri-time-line ri-md text-gray-400 ml-2"></i>
								<p class="ml-1 font-semibold text-sm text-gray-400">Created 5 days ago</p>
							</div>
						</div>
					</div>
				</div>
				<div class="xs:basis-[100%] sm:basis-[100%] md:basis-[100%]">
					<div class=" rounded-lg border-2">
						<div class="grid grid-flow-row auto-rows-max m-3">
							<div class="flex justify-between">
								<div class="flex ">
									<div class="w-14 h-14 bg-slate-500 rounded-lg bg-cover" style="background-image: url(https://picsum.photos/200/300?random=8)"></div>
									<div class="ml-2">
										<p class="text-lg font-semibold">Senior QA Engineer</p>
										<a href="/" class="text-sm cursor-pointer hover:text-blue-500">Dropsuite</a>
									</div>
								</div>
								<i class="ri-bookmark-line ri-xl hover:text-blue-500 cursor-pointer"></i>
							</div>
							<div class="flex flex-row mt-2 items-center">
								<i class="ri-map-pin-2-fill ri-lg"></i> 
								<p class="font-semibold ml-1">Bandung</p>
							</div>
							<div class="flex flex-row mt-2 items-center">
								<i class="ri-money-dollar-circle-line ri-lg"></i>
								<p class="ml-1 font-semibold text-sm">IDR 10.500.000 - 18.000.000</p>
							</div>
							<div class="flex flex-row mt-2 items-center">
								<i class="ri-briefcase-2-line"></i>
								<p class="ml-1 font-semibold text-sm">3 - 5 years</p>
							</div>
							<div class="flex flex-row mt-2 items-center">
								<button type="button" class="p-1 pr-2 text-xs bg-red-600 rounded-xl text-white flex items-center"><i class="ri-close-line mr-1"></i>Closed</button>
								<i class="ri-time-line ri-md text-gray-400 ml-2"></i>
								<p class="ml-1 font-semibold text-sm text-gray-400">Created 5 days ago</p>
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</div>
