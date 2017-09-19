<template>
    <div class="container-fluid">
        <div id="sidebar">
            <div class="logo">
                <img src="./assets/logo_gold.png"/>
            </div>
            <clock></clock>
            <div class="stats">
                <div class="well">
                    <table>
                        <tr>
                            <td>Today FTD</td>
                            <td>{{ todayFtd }}</td>
                        </tr>
                        <tr>
                            <td>Monthly FTD</td>
                            <td>{{ monthlyFtd }}</td>
                        </tr>
                        <tr>
                            <td>Today deposits</td>
                            <td>{{ todayDeposits }}</td>
                        </tr>
                        <tr>
                            <td>Total deposits</td>
                            <td>{{ totalDeposits }}</td>
                        </tr>
                        <tr>
                            <td>This month goal</td>
                            <td>{{ monthGoal }}</td>
                        </tr>
                    </table>
                </div>
            </div>
        </div>
        <div id="main_table">
            <winners-board></winners-board>
        </div>
    </div>
</template>

<script>
import Clock from './components/Clock'
import WinnersBoard from './components/WinnersBoard'

export default {
    name: 'app',
    data(){
        return {
            todayFtd: 0,
            monthlyFtd: 0,
            todayDeposits: 0,
            totalDeposits: 0,
            monthGoal: "3,000,000$"
        };
    },
    components: {
        Clock,
        WinnersBoard
    }
}
</script>

<style>
@import url(https://fonts.googleapis.com/css?family=Roboto);
body {
    font-family: 'Roboto', sans-serif;
}
#sidebar{
    width: 25%;
    float: left;
    background:
    radial-gradient(black 15%, transparent 16%) 0 0,
    radial-gradient(black 15%, transparent 16%) 8px 8px,
    radial-gradient(rgba(255,255,255,.1) 15%, transparent 20%) 0 1px,
    radial-gradient(rgba(255,255,255,.1) 15%, transparent 20%) 8px 9px;
    background-color:#282828;
    background-size:16px 16px;
    color: #fff;
    padding: 10px;
}
#main_table{
    width: 75%;
    float: left;
}
.logo {
    text-align: center;
}
.logo img {
    margin: 0px auto;
    width: 100%;
    margin-top: 31px;
    margin-bottom: 49px;
}

.well {
    min-height: 20px;
    padding: 10px;
    width: 90%;
    margin-bottom: 20px;
    margin: 0px auto;
    color: #fff;
    border: none;
    border-radius: 5px;
    border: #564949 1px solid;
    background: linear-gradient(27deg, #151515 5px, transparent 5px) 0 5px, linear-gradient(207deg, #151515 5px, transparent 5px) 10px 0px, linear-gradient(27deg, #222 5px, transparent 5px) 0px 10px, linear-gradient(207deg, #222 5px, transparent 5px) 10px 5px, linear-gradient(90deg, #1b1b1b 10px, transparent 10px), linear-gradient(#1d1d1d 25%, #1a1a1a 25%, #1a1a1a 50%, transparent 50%, transparent 75%, #242424 75%, #242424);
    background-color: #131313;
    background-size: 20px 20px;
}
.stats table tr {
    border-bottom: #525151 1px solid;
    font-size: 32px;
}
.stats { 
    margin-top: 67px; 
    margin-bottom: 450px; 
}
.stats table tr td:nth-child(1) { font-weight: bolder; }
.stats table tr td { padding: 7px; }
.stats table { width: 100%; }


.container-fluid{
    padding-left: 0px;
    padding-right: 0px;
}
</style>
