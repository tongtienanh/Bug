<template>
<div>
    <div>Tab {{ tab }}</div>
    <div v-if="tab == 1">
        <div v-for="(item, index) in scheduleInfo" :key="index">{{ item.id }} - {{ item.name }}</div>
    </div>
</div>
</template>

<script>
    export default {
        name: "Item",
        props: ["tab"],
        data: function () {
            return {
                scheduleInfo: null
            }
        },
        created() {
            console.log(`${this.tab} is created.`);
            if (this.tab == 1) {
                this.fetchData();
            }
            
        },
        destroyed() {
            console.log(`${this.tab} is destroyed.`)
        },
        mounted() {
            console.log(`${this.tab} is mounted.`)
        },
        updated() {
            console.log(`${this.tab} is updated.`);
        },
        watch: {
            tab: function (val, old) {
                console.log(`New: ${val}, ${old}`);
                if (this.tab == 1) {
                    this.fetchData();
                }
            }
        },
        methods: {
            fetchData: async function() {
                console.log("this.fetchData", this.tab);
                this.scheduleInfo = [
                    { id: 1, name: "Schedule 1" },
                    { id: 2, name: "Schedule 2" },
                    { id: 3, name: "Schedule 3" },
                ];
            }
        }
    }
</script>