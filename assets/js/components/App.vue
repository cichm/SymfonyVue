<template>
    <div>
        <div class="card m-2" style="width: 40rem;">
            <div class="card-body">
                <h5 class="card-title" v-text="thecardtitle"></h5>
                <button @click="sendMessage" class="btn btn-info">Send Child A Message</button>
                <child-card :parentmessage="parentmessage" @finished="finished"></child-card>
            </div>
        </div>
    </div>
</template>

<script>
    import ChildCard from './child/ChildCard';

    export default {
        components: {ChildCard},

        data() {
            return {
                thecardtitle: 'Parent Component!',
                parentmessage: ''
            }
        },

        methods: {
            sendMessage() {
                this.parentmessage = '<b>Message From Parent:</b> Do Your Homework'
            },

            finished() {
                this.parentmessage = ''
            }
        }
    }
</script>

<style>
</style>
