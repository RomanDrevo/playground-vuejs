<template>
    <div id="score_board">
        <winner v-for="winner in winners"
            :info="winner"></winner>
    </div>
</template>

<script>
import Pusher from 'pusher-js';
import Winner from './Winner';
require('howler');

export default {
    name: 'winners-board',
    created(){
        this.registerSounds();
        this.registerToPuhser();
    },
    data () {
        return {
            sound: {},
            winners: [
                {name: "Test User", desk: "FTD Morning Shift", deskType: "FTD", time: "20:30", amount: "1,000$", amountType: "USD"},
                {name: "Test User", desk: "FTD Morning Shift", deskType: "FTD", time: "20:30", amount: "1,000$", amountType: "USD"},
                {name: "Test User", desk: "FTD Morning Shift", deskType: "FTD", time: "20:30", amount: "1,000$", amountType: "USD"}
            ]
        };
    },
    components: {
        Winner
    },
    methods: {
        registerSounds(){
            this.sound = new Howl({
                src: ['/static/bell_ring.mp3']
            });
        },
        registerToPuhser(){
            let pusher = new Pusher('289f04502d73dc29773d', { encrypted: true });
            let channel = pusher.subscribe('my-channel');
            channel.bind('my-event', (data) => { 
                //play the sound * 5
                //display the video
                this.winners.unshift(data); 
                this.sound.play();
                //animate the first row 2 seconds
            });
        }
    }
}
</script>

<style scoped>
div#date_wrap {
    text-align: center;
    font-size: 24px;
}

div#live_clock {
    text-align: center;
    font-size: 43px;
    font-family: 'Rboto', sans-serif;
}
</style>
