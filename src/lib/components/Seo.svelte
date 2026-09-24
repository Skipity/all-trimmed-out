<script>
    export let title;
    export let description;
    export let path = '/';

    const siteUrl = 'https://alltrimmedoutfl.com';
    const image = `${siteUrl}/images/Showroom20251204_104052.webp`;
    $: canonical = `${siteUrl}${path}`;
</script>

<svelte:head>
    <title>{title}</title>
    <meta name="description" content={description} />
    <link rel="canonical" href={canonical} />
    <meta property="og:type" content="website" />
    <meta property="og:locale" content="en_US" />
    <meta property="og:site_name" content="All Trimmed Out" />
    <meta property="og:title" content={title} />
    <meta property="og:description" content={description} />
    <meta property="og:url" content={canonical} />
    <meta property="og:image" content={image} />
    <meta property="og:image:alt" content="All Trimmed Out showroom in Clearwater, Florida" />
    <meta name="twitter:card" content="summary_large_image" />
    <meta name="twitter:title" content={title} />
    <meta name="twitter:description" content={description} />
    <meta name="twitter:image" content={image} />
    <meta name="twitter:image:alt" content="All Trimmed Out showroom in Clearwater, Florida" />
</svelte:head>
