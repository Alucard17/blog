<script>
    import Sidebar from '../components/Sidebar.svelte';
    
	export let segment;
</script>

<style>
</style>

<div class="content container">
    <Sidebar />
    <slot></slot>
</div>