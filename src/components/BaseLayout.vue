<template>
<header>
<div id="container">
    <div class="div1">
    <a href="https://www.google.com">
    <img class="link1" src="../assets/google.png">
    </a>
    </div>
    <div class="div2">
    <h1>HomePage Component</h1>
    </div>
    <div class="div3">
    <a href="https://www.efrei.fr">
    <img class="link2" src="../assets/efrei.png">
    </a>
    </div>
    </div>
    </header>
    <slot name="default"></slot>
    <footer>
    <p>Legal credits| @2022</p>
    
    </footer>
</template>


<style>
#container{
    display:flex;
    justify-content: space-between;
    background-color:blue;
}
.div1{
     margin-top:20px;
    height:20%;
    width:20%;
}
.div2{
    margin-left:400px;
    

    height:20%;
    width:20%;
}
.div3{
    margin-left:200px;
    margin-top:20px;
    height:40%;
    width:40%;
}
.link1{
  height:20%;
  width:20%;
}
h1{
    margin:50 px;
    height:20%;
  width:20%;
}
.link2{
    height:40%;
  width:40%;
}
header{
    position:absolute;

    top:0;

    width:100%;
}
footer{
    background:#ccc;
    position:absolute;

    bottom:0;

    width:100%;
}
</style>