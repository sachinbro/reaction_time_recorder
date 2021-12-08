<template>
  <p>Reaction time - {{score}}ms</p>
  <p> Remark: {{rank}}</p>
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
        if(this.score <150){
            this.rank = "Vutte level Reflex"
        }
        else if(this.score < 250){
            this.rank = "Thikai ho"
        }
        else {
            this.rank = "Thukka bejati"
        }
    }
}
</script>

<style scoped>
    
</style>