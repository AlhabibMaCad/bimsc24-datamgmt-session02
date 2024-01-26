<!-- the script is where the js code goes -->
<script setup>
import { onMounted, ref } from "vue" // you need this to use ref()

  //Change background color
  const doc = document.documentElement;
  doc.style.background = "orange";
  doc.style.fontFamily = "monospace";
  doc.style.fontSize = "15px";

function makeBackgroundWhite() {
    doc.style.background = "white";
}
function makeBackgroundOrange() {
    doc.style.background = "orange";
}



// test for access sidebar
//   document.addEventListener("DOMContentLoaded", function() { 
//   const side = document.getElementById("sidebar");
//   console.log(side);
//   side.style.background = "gray";
// });

// test for access main text innerHTML not working
//   document.addEventListener("DOMContentLoaded", function() { 
//   const main = document.getElementById("main");
//   console.log(main)
//   main.style.background = "gray"
//   main.innerHTML = textInput
// });


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
// document.addEventListener("DOMContentLoaded", function() { 


// function changemaincolor() {
//     console.log(divNameInput.value)
//     let mySelectedDiv = document.getElementById(divNameInput.value)
//     mySelectedDiv.style.backgroundColor = colorInput.value
// }
// });


onMounted(() => {
    changecolor = () =>{
        let mySelectedDiv = document.getElementById(divNameInput.value)
        mySelectedDiv.style.background = colorInput.value
    };

})

// this one not working the function to be written in this way
// onMounted(() => {
//     function changemaincolor (){
//         let mySelectedDiv = document.getElementById(divNameInput.value)
//         mySelectedDiv.style.background = colorInput.value
//     };

// })


</script>



<!-- the template is where the html code goes -->
<template>

<div id="navbar" class="container">  
        <div id="title">Abdulrahman alhabib CBDM assignment 02</div>
    </div>

    <div id="flex">
        <div id="sidebar" class="container"> Sidebar 
            <br/>
            <button @click="makeBackgroundWhite">
                white background
            </button>
            <br/>
            <button @click="makeBackgroundOrange">
                orange background
            </button>

            <br/>
            <input v-model="textInput" type="text" placeholder="write here!">
            <br/>
            <button @click="addToMainTxt">
                add To Main Txt
            </button>
            <br/>
            <input v-model="divNameInput" type="text" placeholder="main/sidebar/navbar">
            <br/>
            only write one of : main / sidebar / navbar
            <br/>
            <input v-model="colorInput" type="text" placeholder="write color here!">
            <br/>
            <button @click="changecolor">
                Do the magic!
            </button>


        </div>
        <div id="main" class="container" :style="{ backgroundColor: colorMain }"> main
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

</style>


