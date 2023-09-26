<!-- <script lang="ts">
    export let data: { items: [] };

    console.log(data);
</script>

<svelte:head>
    <title>Homepage | LazyBytez</title>
    <meta
        name="description"
        content="LazyBytez is a team of enthusiastic software developers creating and maintaining some free time projects."
    />
</svelte:head>

<div class="text-center"> lg:max-w-7xl = w-80 h-80 on monitors with specific height -->

<!-- Container for Grid and Cards -->

<script lang="ts">
	import * as Table from '$lib/components/ui/table';

	export let data: { items: [] };

	const gw2unidItems = data.items;
</script>

<svelte:head>
	<title>Homepage | GW2 Unidentified Items</title>
	<meta
		name="description"
		content="Here you can find a list of all current values of GW2 Unidentified Item salvage results."
	/>
</svelte:head>

<main class="lg:mb-26 m-auto mb-16 md:max-w-3xl lg:max-w-4xl">
	<Table.Root>
		<Table.Caption>Source: https://www.gw2tp.com/</Table.Caption>
		<Table.Header>
			<Table.Row>
				<Table.Head class="w-[100px]">ID</Table.Head>
				<Table.Head class="text-left">Name</Table.Head>
				<Table.Head class="text-left">Cost</Table.Head>
				<!-- <Table.Head class="text-right">Amount</Table.Head> -->
			</Table.Row>
		</Table.Header>
		<Table.Body>
			{#each gw2unidItems as item, i (i)}
				<Table.Row>
					<Table.Cell class="font-medium">{item[0]}</Table.Cell>
					<Table.Cell class="text-left">{item[1]}</Table.Cell>
					<Table.Cell class="text-left">{item[2]}</Table.Cell>
				</Table.Row>
			{/each}
		</Table.Body>
	</Table.Root>
</main>
