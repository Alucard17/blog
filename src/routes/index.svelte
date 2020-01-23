<script context="module">
	export function preload({ params, query }) {
		return this.fetch(`blog.json`).then(r => r.json()).then(posts => {
			return { posts };
		});
	}
</script>

<script>
	export let posts;
</script>

<style>
    .article{
        margin-bottom: 1.75rem
    }
	.post-date{
        margin-bottom: 0.2rem
    }
</style>

<svelte:head>
	<title>Blog</title>
</svelte:head>

<h1>Blog</h1>
<hr />
<div class="article-list">
    {#each posts as post}
        <div class="article">
            <a href="/{post.slug}"><h3 class="post-title">{post.title}</h3></a>
            <span class="post-date">{ new Date(post.date).toDateString() }</span>
            <p>{ post.description }</p>
        </div>
    {/each}
</div>