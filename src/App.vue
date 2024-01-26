<!-- the script is where the js code goes -->
<script setup>
import { onMounted, ref } from "vue" // you need this to use ref()

  //Change background color
  const doc = document.documentElement;
  doc.style.background = "#00796B";
  doc.style.fontFamily = "monospace";
  
  var makeBackgroundDark = null;
  var makeBackgroundBright = null;


onMounted(() => {
    makeBackgroundDark= () =>{
    doc.style.background = '#00796B';
    let mainb = document.getElementById("main")
    mainb.style.borderColor = '#80CBC4';
    mainb.style.webkitTextFillColor = '#80CBC4';
    let titleb = document.getElementById("title")
    titleb.style.webkitTextFillColor = '#80CBC4';
    
}
 makeBackgroundBright = () =>{
    doc.style.background = "#80CBC4";
    let mainb = document.getElementById("main")
    mainb.style.borderColor = '#00796B';
    mainb.style.webkitTextFillColor = '#00796B';
    let titleb = document.getElementById("title")
    titleb.style.webkitTextFillColor = '#00796B';
}


})

// main text adding 
const mainTxt = ref("");
const textInput = ref("");
function addToMainTxt() {
   mainTxt.value += textInput.value;
}

// coloring 
const colorMain = ref("")
const colorInput = ref("");
const divNameInput = ref("")
var changecolor = null

// using this function to insure the DOM is loaded before fire the fuction . 
// also the function syntax is diffrent 
onMounted(() => {
    changecolor = () =>{
        let mySelectedDiv = document.getElementById(divNameInput.value)
        mySelectedDiv.style.background = colorInput.value
        console.log(mySelectedDiv);
    };

})

</script>



<!-- the template is where the html code goes -->
<template>

<div id="navbar" class="container">  
        <div id="title"  >
            ABDULRAHMAN ALHABIB
            <br/>
            CBDM assignment 02
        </div>
        <div id="logo">
            <img src="./profilepic.png" alt="profilepic">
        </div>
    </div>
    <div id="maincontainer" >
    <div id="main" class="container" >main
            <br/>
            {{mainTxt}} </div>
        </div>
    <div id="flex">
        <div id="sidebar" class="container"> Sidebar 
            <br/>
            <h3> change background color! </h3>
            <button @click="makeBackgroundDark">
                dark background
            </button>
            <br/>
            <button @click="makeBackgroundBright">
                bright background
            </button>
            <br/>
            <br/>
            <br/>
            <h3> infinity text adding </h3>
            <input class="inputbox" v-model="textInput" type="text" placeholder="write here!">
            <br/>
            <button @click="addToMainTxt">
                add To Main Txt
            </button>
            <br/>
            <br/>
            <br/>
            <h3>change specific box color</h3>
            <h5>main / sidebar / navbar</h5>
            <input class="inputbox" v-model="divNameInput" type="text" placeholder="main/sidebar/navbar">
            <br/>
            <input class="inputbox" v-model="colorInput" type="text" placeholder="write color here!">
            <br/>
            <button @click="changecolor">
                Do the magic!
            </button>


        </div>
        
    </div>


</template>



<!-- style is where the css code goes -->
<style scoped>
html{
    
    background-color: rgb(59, 59, 59); 
    color: white;
}

body{

    margin:0;
}

div{

    /* put the borders in the inside of container */
    box-sizing: border-box;
}

img{

    height: 85%;
    width: auto;
margin: 5px;
}


.container{
    width: 100%;
    float: right;
    border-width: 1px;
}

#navbar{
    width: calc(98% - 250px);
    height: 50px;
    border-color: rgb(77, 6, 6);
    border-style: hidden;
    float: right;
    box-sizing: border-box;
}

#title{
    color: #80CBC4;
    width: 70%;
    float:left;
    font-size: 18px;
    font-weight: bolder;
}

#logo{
    width: 30%;
    height: 100%;
    float:right;
    text-align: right;
}

#maincontainer{
    width: calc(98% - 250px);
    height: calc(100vh - 50px );;
    float:right;
    border-color: aqua;
    text-align: right;

}
#main{
    width: 100%;
    word-break:break-all;
    border-color: #80CBC4;
    color: #80CBC4;
    font-size:xx-large;
    height: calc(99%);
    border-style: groove;
    border-radius: 20px;
    text-align: center;
margin-inline: 1%;

}

#flex{
    width: 250px;
    display: flex;
    /* height: calc(100vh - 50px); */
    height: calc(100vh);
}

#sidebar{
    border-color: #00796B;
    border-width : thick;
    border-style: solid;
    width: 250px;
    border-radius: 20px;
    background-color: rgb(204, 255, 238);
    margin: 1%;
    text-align: center;
    box-sizing: border-box;


}






.inputbox{
    width: 95%;
    text-align: center;
    margin: auto;
    align-items: center;
}
</style>


