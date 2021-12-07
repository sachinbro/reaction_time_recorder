<template>
  <p>Reaction time - {{score}}ms</p>
  <p> {{rank}}</p>
</template>

<script>
export default {
    props: ['score'],
    data(){
        return {
            rank: null
        }
    },
    mounted(){
        if(this.score <250){
            this.rank = "Vutte lel Reflex"
        }
        else if(this.score < 400){
            this.rank = "Thikai ho"
        }
        else {
            this.rank = "Thukka"
        }
    }
}
</script>

<style>

</style>