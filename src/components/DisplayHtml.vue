<template>
    <div class="classObject" > 
        <v-container justify="center">
            <div v-html="html">  </div>
        </v-container>
    </div>
</template>

<script>
export default {
 props: ['html'],
 data : function () {
    return {
        testData: ''
    }
  }
}
</script>


<style scoped>
.classObject{
    outline-style: solid;
    margin-left: 80px;
    margin-right: 80px;
}
</style>