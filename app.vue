<template>
    <NuxtLayout>
        <NuxtPage />
    </NuxtLayout>
</template>

<script setup>
    const route = useRoute()
    useHead({
        htmlAttrs: {
            lang: 'en',
        },
        title: route.meta.title ? `${route.meta.title} | Yoswaris Lawpaiboon` : 'Yoswaris Lawpaiboon',
        link: [
            { rel: 'preconnect', href: 'https://fonts.googleapis.com' },
            { rel: 'preconnect', href: 'https://fonts.gstatic.com', crossorigin: true },
            { rel: 'stylesheet', href: 'https://fonts.googleapis.com/css2?family=Noto+Sans+Thai:wght@300&family=Roboto&display=swap', rel: 'stylesheet' },
        ],
    })
</script>
