<template>
    <div class="h-96 w-full">
        <div class="message-container">
            <div v-for="(message, index) in messages" :key="index">
                <message-item :message="message"/>
            </div>
        </div>
    </div>
</template>

<script>
    import MessageItem from "./messageItem";

    export default {
        name: "messageContainer",
        components: {MessageItem},
        props: ["messages"]
    }
</script>

<style scoped>
.message-container{
    display: flex;
    flex-direction: column-reverse;
    align-items: flex-start;
    height: 100%;
    margin-left: 15px;;
}
</style>
