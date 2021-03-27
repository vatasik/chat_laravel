<template>
    <div class="relative h-10 m-1">
        <div style="border-top: 1px solid grey;" class="grid grid-cols-6">
            <input
                type="text"
                v-model="message"
                @keyup.enter="sendMessage()"
                placeholder="Type message here"
                class="col-span-5 outline-none p-1 input-message"
            />
            <button
                @click="sendMessage()"
                class="place-self-end bg-green-600 hover:bg-green-500 p-1 mt-1 rounded text-white">
                Send
            </button>

        </div>
    </div>
</template>

<script>
    import Input from "../../../../vendor/laravel/jetstream/stubs/inertia/resources/js/Jetstream/Input";
    import Button from "../../../../vendor/laravel/jetstream/stubs/inertia/resources/js/Jetstream/Button";

    export default {
        name: "inputMessage",
        components: {Button, Input},
        props: ['room'],
        data: function () {
            return {
                message: ''
            }
        },
        methods: {
            sendMessage() {
                axios.post('/chat/rooms/' + this.room.id + '/messages', {
                    message: this.message
                })
                    .then(response => {
                        if (response.status === 201) {
                            this.message = '';
                            this.$emit('messagesent');
                        }
                    })
                    .catch(error => {
                        console.log(error)
                    })

            }
        }
    }
</script>

<style scoped>
    .input-message {
        border: none;
    }
</style>
