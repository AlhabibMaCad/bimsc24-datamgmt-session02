<!-- the script is where the js code goes -->
<script setup>
import { onMounted, ref } from "vue" // you need this to use ref()

  //Change background color
  const doc = document.documentElement;
  doc.style.background = "orange";
  doc.style.fontFamily = "monospace";
  

function makeBackgroundWhite() {
    doc.style.background = "white";
}
function makeBackgroundOrange() {
    doc.style.background = "orange";
}


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
    };

})


</script>



<!-- the template is where the html code goes -->
<template>

<div id="navbar" class="container">  
        <div id="title">
            Abdulrahman alhabib CBDM assignment 02
        </div>
        <div id="logo">
            <img src="./profilepic.png" alt="profilepic">

        </div>
    </div>

    <div id="flex">
        <div id="sidebar" class="container"> Sidebar 
            <br/>
            <h3> change background color! </h3>
            <button @click="makeBackgroundWhite">
                white background
            </button>
            <br/>
            <button @click="makeBackgroundOrange">
                orange background
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
        <div id="main" class="container" > main
            <br/>
            {{mainTxt}} </div>
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

    height: 100%;
    width: auto;

}

#navbar{

    height: 50px;
    border-color: red;


}

#flex{
    
    display: flex;
    height: calc(100vh - 50px);
}

#sidebar{
    
    width:30%;
    border-color: blue;

}

#main{
    width:70%;
    border-color: green;

}

#title{
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

.container{

    border-style: dotted;
    border-width: 1px;

}

.inputbox{
    width: 95%;


}
</style>


