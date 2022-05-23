<template>
    <div>
        <img alt="logo" src="../assets/logo.png" />
        <p>{{ defaultText }}</p>
    </div>
</template>

<script>
export default {
    name: "PopupTitle",
    mounted() {
        browser.runtime.sendMessage({});
    },
    computed: {
        defaultText() {
            return browser.i18n.getMessage("extName");
        },
    },
};
</script>

<style scoped>
div {
    text-align: center;
}

p {
    font-size: 20px;
}
</style>
