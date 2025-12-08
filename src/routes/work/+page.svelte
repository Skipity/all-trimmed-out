<script>
    const images = [
        "/images/work/20251202_074821.webp",
        "/images/work/20251202_074850.webp",
        "/images/work/20251202_074911.webp",
        "/images/work/20251202_074930.webp",
        "/images/work/20251202_074930_1.webp",
        "/images/work/20251202_075031.webp",
        "/images/work/20251202_075055.webp",
        "/images/work/20251202_075142.webp",
    ];
</script>

<svelte:head>
    <title>Our Work | All Trimmed Out</title>
    <meta
        name="description"
        content="View examples of our premium door, millwork, and trim installations. See the quality and craftsmanship we bring to every project."
    />
</svelte:head>

<div class="bg-white min-h-screen font-sans text-neutral-900">
    <!-- Navbar (Simplified version of main nav) -->
    <nav
        class="sticky top-0 z-50 bg-white/90 backdrop-blur-md shadow-sm border-b border-neutral-100"
    >
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-20">
                <div class="flex-shrink-0 flex items-center">
                    <a href="/">
                        <img
                            class="h-12 w-auto"
                            src="/images/all-trimmed-out-logo.jpg"
                            alt="All Trimmed Out Logo"
                        />
                    </a>
                </div>
                <div class="hidden md:flex space-x-4">
                    <a
                        href="/#products"
                        class="px-4 py-2 bg-red-700 text-white font-bold rounded hover:bg-blue-900 transition-colors shadow-sm"
                        >Products</a
                    >
                    <a
                        href="/#about"
                        class="px-4 py-2 bg-red-700 text-white font-bold rounded hover:bg-blue-900 transition-colors shadow-sm"
                        >Our Facility</a
                    >
                    <a
                        href="/#contact"
                        class="px-4 py-2 bg-red-700 text-white font-bold rounded hover:bg-blue-900 transition-colors shadow-sm"
                        >Contact</a
                    >
                </div>
            </div>
        </div>
    </nav>

    <main class="max-w-7xl mx-auto py-16 px-4 sm:px-6 lg:px-8">
        <div class="text-center mb-16">
            <h1 class="text-4xl font-extrabold text-neutral-900 sm:text-5xl">
                Recent Projects
            </h1>
            <p class="mt-4 text-xl text-neutral-500 max-w-2xl mx-auto">
                Explore our portfolio of custom installations, hardware, and
                speciality doors.
            </p>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            {#each images as src}
                <div
                    class="rounded-xl overflow-hidden shadow-lg hover:shadow-2xl transition-shadow duration-300 group"
                >
                    <div
                        class="aspect-w-4 aspect-h-3 bg-neutral-100 overflow-hidden"
                    >
                        <img
                            {src}
                            alt="Project Example"
                            class="w-full h-full object-cover transform group-hover:scale-105 transition-transform duration-500"
                        />
                    </div>
                </div>
            {/each}
        </div>

        <div class="mt-16 text-center">
            <a
                href="/#contact"
                class="inline-flex items-center justify-center px-8 py-4 border border-transparent text-lg font-bold rounded-md text-white bg-blue-700 hover:bg-blue-800 transition-all shadow-xl hover:scale-105"
            >
                Start Your Project
            </a>
        </div>
    </main>

    <footer class="bg-neutral-900 border-t border-neutral-800 mt-24">
        <div
            class="max-w-7xl mx-auto py-12 px-4 sm:px-6 md:flex md:items-center md:justify-between lg:px-8"
        >
            <div class="flex justify-center md:order-2 space-x-6">
                <span class="text-neutral-400 text-sm"
                    >© {new Date().getFullYear()} All Trimmed Out. All rights reserved.</span
                >
            </div>
            <div class="mt-8 md:mt-0 md:order-1 text-center md:text-left">
                <a href="/">
                    <img
                        src="/images/all-trimmed-out-logo.jpg"
                        alt="Logo"
                        class="h-10 opacity-50 grayscale hover:grayscale-0 transition-all mx-auto md:mx-0"
                    />
                </a>
            </div>
        </div>
    </footer>
</div>
