<template>
  <div class="hello">
    <button @click="updatetabemono('tainootukuri')">update</button><br/>
    <!-- {{kaisenList}} -->
    {{kaisenList2}}
    <h1>{{ msg }}</h1>
    {{myVar}}
    {{kaisenn}}
    <br/>
    <button @click="updateText('Hello World!!')">update</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data: function(){
    return {
      myVar: "hogehoge",
      kaisenn:[
       { menyu: ["kaisenndonn", "osasimi", "agemono"] }
      ]
    }
  },
  methods:{
    updateText: function(text){
      this.myVar = text;
      let myvar = "jpgajpga";
      console.log(myvar)
    },
    updatetabemono: function(text){
      this.kaisenn[0].menyu[3] = text;
      this.kaisenn[0].menyu.push(text);
      console.log(this.kaisenn)
    }
  },
  computed: {
    kaisenList: function(){
      return this.kaisenn[0].menyu.join(" / ")
    },
    kaisenList2: function(){
      alert("海鮮が更新されました。")
      console.log(this.myVar)
      return this.kaisenn[0].menyu
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
</style>
