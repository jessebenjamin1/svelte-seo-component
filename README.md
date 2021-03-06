# Svelte SEO Component

This is a component which can be used to set common meta tags in the <code>head</code> of pages in a Svelte app.

You can set a default title, description, and image in the component itself. When using the component. It is recommended to always pass <code>title</code> and <code>description</code> as props to avoid duplicate titles and metadescriptions. These props will set title & description meta tags, as well as associated Open Graph & Twitter tags.

This component also accepts Open Graph- & Twitter-specific props that will override the generic <code>title</code> and <code>description</code> values if passed.

The logic of the component assumes that the default value for <code>image</code> and <code>alt</code> are set for a global default sharing image. I recommend adding your default share image to the static folder in Sveltekit projects - that's why all of the image props include static in their path.

Here's an example of a very standard instance of the component, assuming that all of the default values have been changed to be relevant to the project:

```svelte
<SEO
	title="About Page | MDSvex Starter Blog"
	description="This is a starter Sveltekit blog with support for MDSvex & image optimisation via Vite ImageTools."
	slug="/about/"
/>
```

If you really wanted to, you could have different titles, descriptions, and images for Search Engines, Facebook, and Twitter 🤷 Here's what that would look like:

```svelte
<SEO
	title="Manually Set Title | Website Name"
	ogTitle="Facebook Title | Website Name"
	twitterTitle="Twitter Title | Website Name"
	description="I'm a manually set meta description."
	ogDescription="I will override the og:description tag."
	twitterDescription="I will override the twitter:description tag."
	image="/static/iWillSetOgAndTwitterImageTags.jpg"
	ogImage="/static/iWillOverrideOgImageTag.jpg"
	ogImageAlt="manual alt text for OG image"
	twitterImage="/static/iWillOverrideTwitterImageTag.jpg"
	twitterImageAlt="manual alt text for Twitter image"
	slug="/"
/>
```
