Html Side

<!DOCTYPE html>
<html>
<head>
   <title>Split Landing Page</title>

<link rel="stylesheet" href="main.css">


</head>
    
<body>

 <div class="container">
    
  <div class="split left">
     
    <h1>The Designer</h1> 
     <a href="#" class="button">Read More</a>
     </div>  
    
    
    <div class="split right"><h1>The Programmer</h1> 
     <a href="#" class="button">Read More</a></div>
</div>   






<script src="script.js"></script>
</body>
</html>



:root{

--container-bg-color: #333;
--left-bg-color : rgba(223,39,39, 0.7);
--right-bg-color : rgba(43,43,43, 0.8);
--left-button-hover-color: rgba(161,11,11, 0.3);
--right-button-hover-color: rgba(92,92,92,0.3);
--hover-width: 75%;
--other-width: 25%;
--speed:1000ms;    
    
}

html,body{
padding:0;
margin: 0;
font-family: cursive;
width: 100%;
height: 100%;
overflow-x: hidden;

    
}

h1{
font-size:4rem;
color: white;
position: absolute;
left: 50%;
top: 20%;
transform: translateX(-50%);
white-space: nowrap;

    
    
}

.button{
display: block;
position: absolute;
top: 50%;
left:50%;
text-align: center;
height: 2.5rem;
width: 15rem;
padding-top: 1.3rem;
color: #fff;
border: #fff solid 0.2rem;
font-size: 1rem;
font-weight: bold;
text-transform: uppercase;
text-decoration: none;
transform: translateX(-50%);

}

.split.left .button:hover{
background-color: var(--left-button-hover-color);    
border-color:var(--left-button-hover-color);    
}

.split.right .button:hover{
background-color: var(--right-button-hover-color);    
border-color:var(--right-button-hover-color);    
}

.container{
 position: relative;   
 width:100%;
height:100%;
background-color:var(--container-bg-color);
}

.split{
 position: absolute;
width: 50%;
height: 100%;
overflow: hidden;

    
}

.split.left{
 left: 0;
background-image: url(img/img-2.jpg);
background-position: center;
background-size: cover;
    
}

.split.left:before{
position: absolute;
content: "";    
width: 100%;
height: 100%;
background: var(--left-bg-color);
    
    
}

.split.right{
 right: 0;
background-image: url(img/img-1.png);
background-position: center;
background-size: cover;
background-repeat: no-repeat;    
    
}

.split.right:before{
 position: absolute;
content: "";    
width: 100%;
height: 100%;
background: var(--right-bg-color);   
    
}

.split.left, .split.right,.split.left:before, .split.right:before{
    
 transition:var(--speed) all ease-in-out;   
}

.hover-left .left{
 width: var(--hover-width);   
    
}

.hover-left .right{
    
width:var(--other-width);    
}

.hover-left .right:before{
z-index: 2;
}

.hover-right .right{
 width: var(--hover-width);   
    
}

.hover-right .left{
    
width:var(--other-width);    
}

.hover-right .left:before{
z-index: 2;
}

@media(max-width: 800px){
    
    h1{
        
     font-size:1.5rem;   
   
    }   

    .button{
        
        width: 10rem;
    }

}

@media(max-height: 700px){
    
    .button{
        
        top: 70%;
    }       
    
    
}



const left = document.querySelector('.left');
const right = document.querySelector('.right');
const container = document.querySelector('.container');


left.addEventListener('mouseenter',  () => {
                      
container.classList.add('hover-left');                      
                    
});


left.addEventListener('mouseleave', () => {
                      
container.classList.remove('hover-left');                      
                    
});

right.addEventListener('mouseenter', () => {
                      
container.classList.add('hover-right');                      
                    
});


right.addEventListener('mouseleave', () => {
                      
container.classList.remove('hover-right');                      
                    
});
