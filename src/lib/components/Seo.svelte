<script>
import { base } from "$app/paths";

const SITE_NAME = "Leonardo Nicolai";
const SITE_URL = "https://codenicolai.github.io";
const DEFAULT_DESCRIPTION =
	"Portfolio of Leonardo Nicolai, a software engineer and technical lead with 7+ years building React, React Native, and Node.js products.";

/** @type {{ title?: string, description?: string, path?: string, image?: string, type?: string, noindex?: boolean }} */
const {
	title = "",
	description = DEFAULT_DESCRIPTION,
	path = "",
	image = "",
	type = "website",
	noindex = false,
} = $props();

const fullTitle = $derived(title ? `${title} — ${SITE_NAME}` : SITE_NAME);
const canonical = $derived(`${SITE_URL}${base}${path}`);
const ogImage = $derived(image ? `${SITE_URL}${image}` : `${SITE_URL}${base}/github_photo.png`);
</script>

<svelte:head>
  <title>{fullTitle}</title>
  <meta name="description" content={description} />
  <link rel="canonical" href={canonical} />
  {#if noindex}
    <meta name="robots" content="noindex, nofollow" />
  {/if}

  <meta property="og:type" content={type} />
  <meta property="og:site_name" content={SITE_NAME} />
  <meta property="og:title" content={fullTitle} />
  <meta property="og:description" content={description} />
  <meta property="og:url" content={canonical} />
  <meta property="og:image" content={ogImage} />

  <meta name="twitter:card" content="summary_large_image" />
  <meta name="twitter:title" content={fullTitle} />
  <meta name="twitter:description" content={description} />
  <meta name="twitter:image" content={ogImage} />
</svelte:head>
