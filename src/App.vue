<!-- the script is where the js code goes -->
<script setup>
import { ref } from "vue" // you need this to use ref()

  //Change background color
  const doc = document.documentElement;
  doc.style.background = "orange";
  doc.style.fontFamily = "monospace";
  //not working
  //const side = document.querySelector('#sidebar');
  //console.log(side);
  //let maintxt = ref('test');
  //console.log(maintxt)


function makeBackgroundWhite() {
    doc.style.background = "white";
}
function makeBackgroundOrange() {
    doc.style.background = "orange";
}



const mainTxt = ref("");
const mainTxt1 = ref("hi");





//from boot camp ( not working )
//let input1 = document.createElement("input1")
//input1.style.width = "90%"
//input1.style.fontSize = "12px"
//sidebar.appendChild(input)

function addToMainTxt() {
    

}


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
            <input v-model="mainTxt" type="text" placeholder="write here!">
            <br/>
            <button @click="addToMainTxt">
                add To Main Txt
            </button>


        </div>
        <div id="main" class="container"> hi {{ mainTxt }} </div>
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


