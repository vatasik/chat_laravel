<template>
    <div class="w-full">
        {{message.user.name}}: {{message.message}}
    </div>
</template>

<script>
    export default {
        name: "messageItem",
        props: ["message"]
    }
</script>

<style scoped>

</style>
