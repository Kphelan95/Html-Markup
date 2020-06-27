<template>
    <div>
        <v-container class="my-5">
          <v-layout row justify-center>
            <v-card-title>
              <h1 class="display-1" >Enter some HTML</h1>
            </v-card-title>
          </v-layout>
          <div class="grid">
            <v-layout row justify-end> 
                <v-flex md8>
                  <v-textarea
                  class="pa-0"
                  name="input-7-1"
                  label="Enter text here"
                  v-model="messageCPY"
                  v-on:keyup="moveData"
                  clearable
                  hide-details
                  outlined
                  />
                </v-flex>
                <v-flex md3>
                  <v-container fill-height>
                        <div class="d-flex flex-column">
                          <v-btn class="mb-1" color="primary" @click="LoadExsample()" >Load example</v-btn>
                          <v-btn class="mb-1" color="primary" >place holder</v-btn>
                          <v-btn class="mb-1" color="primary" >place holder</v-btn>
                        </div>
                  </v-container>
                </v-flex>
            </v-layout>
          </div>
        </v-container>
    </div>
</template>

<script>
export default {
  name: 'TextBox',
  props: {
    value: {
      
    }
  },
  data : function () {
    return {
        messageCPY: "",
        messageCPY2:""
    }
  },
  methods :{
    moveData(){
        this.messageCPY2=this.messageCPY;//CPY is the real one
        this.$emit('changeBack',this.messageCPY2);
        //inner html
    },
    LoadExsample(){
      this.messageCPY=`<h1>HTML example </h1>
        <p><b>Radio Input</b><br />
        <input type="radio"  />Love Radio Buttons
        <input type="radio" />Hate Radio Buttons</p>
        <p><b>Checkbox Input</b>
        <input type="checkbox" />Love Checkboxs
        <input type="checkbox" />Hate Checkboxs</p>
        <p><b> Red Button</b>
        <button type="button" style="background-color: #f44336; color: white;">Click Me!</button>
        <p><b> Bulleted List </b>
        <ul>
          <li>Coffee</li>
          <li>Tea</li>
          <li>Milk</li>
        </ul>`
    this.$emit('changeBack',this.messageCPY);
    }
  }
}
</script>

<style scoped>
</style>