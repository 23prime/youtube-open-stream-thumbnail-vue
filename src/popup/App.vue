<template>
    <div>
        <popup-title class="item" />
        <open-button class="item" />
    </div>
</template>

<script>
import PopupTitle from "@/components/PopupTitle.vue";
import OpenButton from "@/components/OpenButton.vue";

export default {
    name: "App",
    components: { PopupTitle, OpenButton },
};
</script>

<style>
html {
    width: 360px;
    height: 360px;
}

.item {
    padding: 32px 0;
}
</style>
