<template>
    <nav class="pr-8">
        <NuxtLink :to="localePath( 'about', locale ) " class="px-2 py-1">{{t('menu.about')}}</NuxtLink>
        <NuxtLink :to="localePath( 'modules', locale )" class="px-2 py-1">{{t('menu.modules')}}</NuxtLink>
    </nav>
</template>

<script setup>
    const { locale, locales, t } = useI18n({
        useScope: 'global'
    })
    const localePath = useLocalePath()
    
    const availableLocales = computed(() => {
        return (locales.value).filter(i => i.code !== locale.value)
    })
    
</script>



<style scoped>
/* home route and active route will show in bold as it matches / and /about */
    a.router-link-active {
        /* font-weight: bold; */
        font-weight: 700;
        border-bottom:1px solid black !important;
    }
/* exact link will show the primary color for only the exact matching link */
    /* a.router-link-exact-active {
        color: #00c58e;
    } */
</style>