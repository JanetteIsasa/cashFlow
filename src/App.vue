<template>

    <Suspense>
        <template #default>
            <Home />
        </template>
        <template #fallback>
            <SplashScreen />
        </template>
    </Suspense>

</template>

<script>

import SplashScreen from '@/components/SplashScreen.vue';
import { defineAsyncComponent } from "vue";

export default {
    components: {
        SplashScreen,
        Home: defineAsyncComponent(() => {
            return new Promise((resolve) => {
                setTimeout(() => {
                    resolve(import("./components/Home.vue"));
                }, 2500);
            });
        }),
    },
};
</script>

<style>
html,
body,
.app {
    min-height: 100vh;
    margin: 0;
    font-family: Arial, Helvetica, sans-serif;
    
}
body{
    background-color: var(--brand-celeste);;
}

* {
    --brand-celeste: #4d7d91;
    --brand-celeste-claro: #a3c8db;
    --brand-celeste-claro2: #e5ecf4;
    --brand-naranja: #fd844b;
    --brand-azul-oscuro: #0b0b23;
}
</style>