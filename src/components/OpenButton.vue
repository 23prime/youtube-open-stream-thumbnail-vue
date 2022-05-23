<template>
    <div class="content">
        <v-btn @click="openThumbnail" :disabled="!this.thumbnailUrl">Open</v-btn>
    </div>
</template>

<script>
export default {
    name: "Current",

    data() {
        return {
            currentUrl: null,
            streamId: null,
            thumbnailUrl: null,
        };
    },

    mounted() {
        browser.runtime.sendMessage({});

        chrome.tabs.query({ active: true, currentWindow: true }, (tabs) => {
            this.currentUrl = new URL(tabs[0].url);
            this.streamId = this.currentUrl.searchParams.get("v");

            if (this.isYouTube()) {
                this.thumbnailUrl = `https://i.ytimg.com/vi/${this.streamId}/maxresdefault.jpg`;
            }
        });
    },

    methods: {
        isYouTube() {
            return this.currentUrl.host.includes("youtube.com") && this.streamId;
        },

        openThumbnail() {
            window.open(this.thumbnailUrl);
        },
    },
};
</script>

<style scoped>
.content {
    text-align: center;
}
</style>
