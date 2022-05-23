<template>
    <div class="home">
        <img alt="logo" src="../assets/logo.png" />
        <Title msg="Welcome to Your Vue.js App" />
    </div>
</template>

<script>
// @ is an alias to /src
import Title from "@/components/Title.vue";

export default {
    name: "Home",
    components: {
        Title,
    },
};
</script>
