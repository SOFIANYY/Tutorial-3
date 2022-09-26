
<template v-slot:default>
<div id="conteneur">
<div class="div1">
<h1 class="homepageHeader" >here is the homepage Component</h1>
</div>
<div class="div2">
<button type="button" class="button1">BaseButton with custom margin</button>
<button type="button" class="button2" disabled>BaseButton disabled</button>
</div>
</div>
</template>

<script>
</script>

<style>
#conteneur{
  display:flex;
  flex-direction:column;
}
.homepageHeader{ 
  margin-left:600px;
}
button:hover{
  color:blue;
}
button:focus{
  background:green;
}
.div2{
  display:flex;
}
button{
  margin: 0 auto;
}
.button1{
  margin-left:130px;
}
.button2{
  margin-left:130px;
}


</style>