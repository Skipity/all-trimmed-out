<script>
    import { page } from "$app/stores";
    import { browser } from "$app/environment";

    let query = "";
    let result = "";

    // Auto-run when someone shares a link like /plum-candy
    $: if (browser && $page.url.pathname !== "/" && $page.url.pathname !== "") {
        query = decodeURIComponent($page.url.pathname.slice(1));
        runCanon();
    }

    function runCanon() {
        if (!query.trim()) {
            result = "";
            return;
        }

        // ←←← YOUR CANON LOGIC GOES HERE ONLY ←←←
        result = `Searching our inventory for ${query.toUpperCase()}... ITEM FOUND IN STOCK.`;
        // ←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←

        if (browser) {
            history.replaceState({}, "", `/${encodeURIComponent(query)}`);
        }
    }

    const products = [
        {
            name: "PlastPro",
            img: "/images/PlastPro20251204_103707.webp",
            desc: "Fiberglass doors that offer the beauty of wood with superior durability.",
            url: "https://www.plastproinc.com",
        },
        {
            name: "Therma-Tru",
            img: "/images/Thuramtru20251204_103823.webp",
            desc: "The nation’s leading manufacturer of fiberglass and steel exterior door systems.",
            url: "https://www.thermatru.com",
        },
        {
            name: "Sterling Doors & Windows (formally Origin)",
            img: "/images/Origin20251204_103718.webp",
            desc: "Premium aluminum bi-fold doors and windows.",
            url: "https://sterlingdw.com",
        },
        {
            name: "Cavity Sliders",
            img: "/images/Cavity Sliders20251204_103739.webp",
            desc: "High quality pocket door hardware and frames.",
            url: "https://www.cavitysliders.com",
        },
        {
            name: "Kwikset",
            img: "/images/Kwikset20251204_103833.webp",
            desc: "Trusted security with style.",
            url: "https://www.kwikset.com",
        },
        {
            name: "L.J. Smith",
            img: "/images/LJ Smith20251204_103916.webp",
            desc: "Distinctive stair systems and wood products.",
            url: "https://www.ljsmith.com",
        },
        {
            name: "Millwork Sales",
            img: "/images/Millwork Sales20251204_103850.webp",
            desc: "Custom millwork solutions.",
            url: "https://millworksales.com",
        },
        {
            name: "Ponderosa",
            img: "/images/Ponderosa20251204_103929.webp",
            desc: "Quality wood doors and millwork.",
            url: "https://ponderosawood.com",
        },
        {
            name: "Woodgrain",
            img: "/images/Woodgrain20251204_103954.webp",
            desc: "One of the largest millwork companies in the world.",
            url: "https://www.woodgrain.com",
        },
        {
            name: "US Lumber",
            img: "/images/US Lumber20251204_104119.webp",
            desc: "Leading distributor of building materials.",
            url: "https://www.uslumber.com",
        },
        {
            name: "Acre",
            img: "/images/Acre exterior product20251204_104014.webp",
            desc: "Sustainable, durable exterior trim and decking.",
            url: "https://modern-mill.com",
        },
        {
            name: "Novo Building Products",
            img: "/images/novobp.webp",
            desc: "Leading manufacturer and distributor of stair parts, mouldings, and specialty millwork.",
            url: "https://www.novobp.com/",
        },
    ];

    const facilities = [
        { name: "Showroom", img: "/images/Showroom20251204_104052.webp" },
        { name: "Warehouse", img: "/images/Warehouse20251204_104148.webp" },
        { name: "Stock", img: "/images/Warehouse20251204_104215.webp" },
        { name: "Facility", img: "/images/Facilty20251204_104314.webp" },
    ];
</script>

<div
    class="min-h-screen bg-neutral-50 font-sans text-neutral-900 selection:bg-blue-600 selection:text-white"
>
    <!-- Navbar -->
    <nav
        class="sticky top-0 z-50 bg-white/90 backdrop-blur-md shadow-sm border-b border-neutral-100"
    >
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-20">
                <div class="flex-shrink-0 flex items-center">
                    <img
                        class="h-12 w-auto"
                        src="/images/all-trimmed-out-logo.jpg"
                        alt="All Trimmed Out Logo"
                    />
                </div>
                <div class="hidden md:flex space-x-4">
                    <a
                        href="#products"
                        class="px-4 py-2 bg-red-700 text-white font-bold rounded hover:bg-blue-900 transition-colors shadow-sm"
                        >Products</a
                    >
                    <a
                        href="#about"
                        class="px-4 py-2 bg-red-700 text-white font-bold rounded hover:bg-blue-900 transition-colors shadow-sm"
                        >Our Facility</a
                    >
                    <a
                        href="#contact"
                        class="px-4 py-2 bg-red-700 text-white font-bold rounded hover:bg-blue-900 transition-colors shadow-sm"
                        >Contact</a
                    >
                </div>
            </div>
        </div>
    </nav>

    <!-- Canon Result Section (Dynamic) -->
    {#if result}
        <section class="bg-blue-50 border-b border-blue-100 py-12">
            <div class="max-w-4xl mx-auto px-4 text-center">
                <h2 class="text-3xl font-bold text-blue-900 mb-2">
                    Search Result
                </h2>
                <div
                    class="p-6 bg-white rounded-xl shadow-lg border border-blue-200"
                >
                    <p class="text-2xl font-mono text-blue-800">{result}</p>
                    <p class="mt-4 text-neutral-600">
                        Contact us immediately to secure this item.
                    </p>
                    <a
                        href="#contact"
                        class="mt-6 inline-block px-8 py-3 bg-blue-700 text-white font-bold rounded hover:bg-blue-800 transition-colors"
                        >Inquire Now</a
                    >
                </div>
            </div>
        </section>
    {/if}

    <!-- Hero Section -->
    <header class="relative bg-white overflow-hidden">
        <div class="max-w-7xl mx-auto">
            <div
                class="relative z-10 pb-8 bg-white sm:pb-16 md:pb-20 lg:max-w-2xl lg:w-full lg:pb-28 xl:pb-32 pt-20 px-4 sm:px-6 lg:px-8"
            >
                <main
                    class="mt-10 mx-auto max-w-7xl sm:mt-12 md:mt-16 lg:mt-20 xl:mt-28"
                >
                    <div class="sm:text-center lg:text-left">
                        <h1
                            class="text-4xl tracking-tight font-extrabold text-neutral-900 sm:text-5xl md:text-6xl"
                        >
                            <span class="block xl:inline"
                                >Florida's Premier Source for</span
                            >
                            <span class="block text-blue-700"
                                >Doors & Millwork</span
                            >
                        </h1>
                        <p
                            class="mt-3 text-base text-neutral-500 sm:mt-5 sm:text-lg sm:max-w-xl sm:mx-auto md:mt-5 md:text-xl lg:mx-0"
                        >
                            At <strong>All Trimmed Out</strong>, we’re more than
                            a door supplier; we’re your trade partner. We
                            support builders and contractors with top-tier,
                            hurricane-rated solutions and the most trusted
                            architectural brands, giving you reliability and
                            confidence so you can deliver exceptional quality
                            results every time.
                        </p>
                        <div
                            class="mt-5 sm:mt-8 sm:flex sm:justify-center lg:justify-start"
                        >
                            <div class="rounded-md shadow">
                                <a
                                    href="#products"
                                    class="w-full flex items-center justify-center px-8 py-3 border border-transparent text-base font-medium rounded-md text-white bg-blue-700 hover:bg-blue-800 md:py-4 md:text-lg transition-all hover:scale-105"
                                >
                                    See Our Collection
                                </a>
                            </div>
                            <div class="mt-3 sm:mt-0 sm:ml-3">
                                <a
                                    href="#contact"
                                    class="w-full flex items-center justify-center px-8 py-3 border border-transparent text-base font-medium rounded-md text-white bg-red-700 hover:bg-blue-900 md:py-4 md:text-lg transition-all"
                                >
                                    Visit Showroom
                                </a>
                            </div>
                        </div>
                    </div>
                </main>
            </div>
        </div>
        <div
            class="lg:absolute lg:inset-y-0 lg:right-0 lg:w-1/2 bg-neutral-100 flex items-center justify-center overflow-hidden lg:pr-8"
        >
            <!-- Hero Image (using one of the nice entrance/showroom shots if possible, or just the logo large) -->
            <img
                class="h-56 w-full object-cover sm:h-72 md:h-96 lg:w-full lg:h-full"
                src="/images/Showroom20251204_104052.webp"
                alt="Showroom Entrance"
            />
        </div>
    </header>

    <!-- Brands/Products Grid -->
    <section id="products" class="py-24 bg-white">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center">
                <h2
                    class="text-base font-semibold text-blue-700 tracking-wide uppercase"
                >
                    Our Partners
                </h2>
                <p
                    class="mt-2 text-3xl leading-8 font-extrabold tracking-tight text-neutral-900 sm:text-4xl"
                >
                    Only the Best Brands
                </p>
                <p class="mt-4 max-w-2xl text-xl text-neutral-500 mx-auto">
                    We partner with top-tier manufacturers to bring you
                    unmatched quality and variety.
                </p>
            </div>

            <div
                class="mt-16 grid gap-8 grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4"
            >
                {#each products as product}
                    <a
                        href={product.url}
                        target="_blank"
                        rel="noopener noreferrer"
                        class="group relative bg-white border border-neutral-200 rounded-lg overflow-hidden hover:shadow-2xl transition-all duration-300 hover:-translate-y-1 block"
                    >
                        <div
                            class="aspect-w-3 aspect-h-2 bg-neutral-200 group-hover:opacity-90 transition-opacity h-48 overflow-hidden"
                        >
                            <img
                                src={product.img}
                                alt={product.name}
                                class="w-full h-full object-cover transform group-hover:scale-110 transition-transform duration-500"
                            />
                        </div>
                        <div class="p-6">
                            <h3
                                class="text-lg font-bold text-neutral-900 group-hover:text-blue-700 transition-colors"
                            >
                                {product.name}
                            </h3>
                            <p class="mt-2 text-sm text-neutral-500">
                                {product.desc}
                            </p>
                        </div>
                    </a>
                {/each}
            </div>
        </div>
    </section>

    <!-- Facilities Section -->
    <section id="about" class="py-24 bg-neutral-900 text-white">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="lg:text-center mb-16">
                <h2
                    class="text-base text-red-500 font-semibold tracking-wide uppercase"
                >
                    Our Scale
                </h2>
                <p
                    class="mt-2 text-3xl leading-8 font-extrabold tracking-tight text-white sm:text-4xl"
                >
                    Stocked & Ready
                </p>
                <p class="mt-4 max-w-2xl text-xl text-neutral-400 lg:mx-auto">
                    Explore our showroom and warehouse to see materials up close
                    while our team helps you evaluate options and plan the best
                    approach for your project.
                </p>
            </div>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                {#each facilities as facility}
                    <div
                        class="relative h-64 sm:h-80 rounded-lg overflow-hidden"
                    >
                        <img
                            src={facility.img}
                            alt={facility.name}
                            class="w-full h-full object-cover hover:scale-105 transition-transform duration-700"
                        />
                        <div
                            class="absolute inset-0 bg-gradient-to-t from-black/80 via-transparent to-transparent flex items-end p-6"
                        >
                            <span class="text-xl font-bold text-white"
                                >{facility.name}</span
                            >
                        </div>
                    </div>
                {/each}
            </div>
        </div>
    </section>

    <!-- CTA / Contact -->
    <section id="contact" class="py-24 bg-blue-700">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
            <h2 class="text-3xl font-extrabold text-white sm:text-4xl">
                Ready to transform your next project?
            </h2>
            <div class="mt-8 flex flex-col items-center">
                <p class="text-white text-xl font-bold mb-2">
                    All Trimmed Out Doors, Millwork, & Trim LLC
                </p>
                <p class="text-blue-100 text-lg mb-6">
                    4501 Ulmerton Road Unit D<br />
                    Clearwater, Fl. 33762
                </p>
                <a
                    href="tel:727-625-8746"
                    class="inline-flex items-center justify-center px-8 py-4 border border-transparent text-lg font-bold rounded-md text-blue-700 bg-white hover:bg-neutral-100 md:py-4 md:text-xl md:px-10 shadow-xl transition-transform hover:scale-105"
                >
                    727-625-8746
                </a>
            </div>
        </div>
    </section>

    <footer class="bg-neutral-900 border-t border-neutral-800">
        <div
            class="max-w-7xl mx-auto py-12 px-4 sm:px-6 md:flex md:items-center md:justify-between lg:px-8"
        >
            <div class="flex justify-center md:order-2 space-x-6">
                <span class="text-neutral-400 text-sm"
                    >© {new Date().getFullYear()} All Trimmed Out. All rights reserved.</span
                >
            </div>
            <div class="mt-8 md:mt-0 md:order-1 text-center md:text-left">
                <img
                    src="/images/all-trimmed-out-logo.jpg"
                    alt="Logo"
                    class="h-10 opacity-50 grayscale hover:grayscale-0 transition-all mx-auto md:mx-0"
                />
            </div>
        </div>
    </footer>
</div>
