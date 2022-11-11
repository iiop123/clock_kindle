<script>
let d=new Date()
export default{
   data(){
  return{
    weekday:["周日",
	"周一",
	"周二",
	"周三",
	"周四",
	"周五",
	"周六"],
  time:''
  }
  },
  methods:{
    time_com(){
    this.time=new Date().toLocaleTimeString()}
  },
 created() {
   setInterval(this.time_com, 1000);
    },
    beforeDestroy() {
      clearInterval(this.time);
    },
  computed:{
    xingqi(){
      return d.toLocaleDateString()+" "+this.weekday[d.getDay()]
    }
  }
}
</script>

<template>
<div class="time">{{time}}</div>
	<div class="xingqi">{{xingqi}}</div>
</template>

<style>
@import url(https://fonts.googleapis.com/css2?family=Roboto:ital,wght@1,900&display=swap);
.time{
			font-size: 13rem;
			font-family: 'Roboto', sans-serif;
			margin-top: 120px;
			text-align: center;
		}
		.xingqi{
			position: fixed;
			right: 0px;
			margin-top: 5%;
			font-size: 450%;
			font-weight: 300;
		}
    
</style>
