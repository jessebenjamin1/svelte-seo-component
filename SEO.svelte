<script>
	export let title = 'Default Title | Applied if no title is passed';
	export let ogTitle;
	export let twitterTitle;
	export let description =
		'This is the default metadescription that will be applied if no description is passed to the SEO component.';
	export let ogDescription;
	export let twitterDescription;
	export let image = '/defaultimage.jpg';
	export let ogImage;
	export let twitterImage;
	export let robots = 'index';
	export let url = 'https://example.com';
	export let slug;
</script>

<svelte:head>
	<!-- General Tags -->
	<title>{title}</title>
	<meta name="description" content={description} />
	<meta name="robots" content={robots} />
	<!-- Open Graph Tags -->
	<meta property="og:title" content={ogTitle ? ogTitle : title} />
	<meta property="og:description" content={ogDescription ? ogDescription : description} />
	<meta property="og:type" content="website" />
	<meta property="og:image" content={ogImage ? `${url}${ogImage}` : `${url}${image}`} />
	<meta property="og:url" content={`${url}${slug}`} />
	<!-- Twitter Tags -->
	<meta property="twitter:title" content={twitterTitle ? twitterTitle : title} />
	<meta
		property="twitter:description"
		content={twitterDescription ? twitterDescription : description}
	/>
	<meta
		property="twitter:image"
		content={twitterImage ? `${url}${twitterImage}` : `${url}${image}`}
	/>
	<meta property="twitter:card" content="summary" />
</svelte:head>
