
    <!DOCTYPE html> <html> 
    <head>
    <style>
		.dropbtn {
    		background-color: #4CAF50;
    		color: white;
    		padding: 16px;
    		font-size: 16px;
    		border: none;
    		cursor: pointer;
			}

		.dropdown {
    		position: relative;
    		display: inline-block;
			}

		.dropdown-content {
    		display: none;
    		position: absolute;
    		background-color: #f9f9f9;
    		min-width: 160px;
    		box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
			}

		.dropdown-content a {
    		color: black;
    		padding: 12px 16px;
    		text-decoration: none;
    		display: block;
			}

		.dropdown-content a:hover {
        	background-color: #f1f1f1;
            }

		.dropdown:hover .dropdown-content {
    		display: block;
			}

		.dropdown:hover .dropbtn {
    		background-color: #3e8e41;
			}

		#extrainfo { 
        	color:#88ffff; top:70px; left:330px; 						
          position:absolute; font-size:12px; 
        	font-family:tahoma;
        	}
        a { color:#ffffff; } 
            
            
    </style>
       
    <script>

         function checkSelection() {
           var Bird=document.getElementById("Birds");
    
            if(Bird.value=="Eagle"){alert('You selected eagle!');}
           if(Bird.value=="Crow"){alert('You selected crow!');}
           if(Bird.value=="Sparrow"){alert('You selected sparrow!');}
           if(Bird.value=="Owl"){alert('You selected owl!');}
            }
       
       
    function ThinkTank(){
        /* Start the Thanks() Function every 2 minutes */
	      var IdeaGuy = setInterval(ThinkTank, 1200000);    
    
        /* Variables for Storing User Input */
	      var Time = Date();
	      var Name = prompt('Did you Blog, today!?', 'Share your Name');
	      var Thought = prompt('Share your Thoughts, '+Name+'!', 'What are you Thinking about?');
	      var TANK = document.getElementById('TANK'); 
        TANK.style.overflow = "auto";
    
        /* Output User Input to the "Gratitude" Division of the webpage */
	      if ( Thought ) { 
        TANK.innerHTML += "<hr>"+Time+ "- " +Name+ ' - is Thinking about : ' +Thought+ "!<p>"; 
                 
        var bubble  = document.createElement("button");
        TANK.appendChild(bubble); 
        bubble.innerHTML="Interesting! &#x263A";
        bubble.setAttribute("id", "Bubble"); 
        
        var thoughtBubble = document.getElementById("Bubble");
        thoughtBubble.style.color="#F00";
                }
        /* Stop the ThinkTank() function */
      }

    </script>
	
    </head>

    <body style="background-image:url('image.png'); background-repeat:no-repeat; background-color:#567;" onload="ThinkTank();" >

	<div class="dropdown">
  	<button class="dropbtn">Dropdown</button>
  		<div class="dropdown-content">
    	<a href="#">Link 1</a>
    	<a href="#">Link 2</a>
    	<a href="#">Link 3</a> 
        </div>
  	</div>

	<div id="extrainfo"> 
    <b>JAVASCRIPT : Web Development + Game Design </b> <br>
        [Buy the Book]:
    <a href="https://www.teacherspayteachers.com/Product/AP-Computer-Science-Principles-JavaScript-3175059">
        CLICK HERE </a>
    </div>

    <div id="TANK" style="background-color:#ff6; width:300px; height:350px; color:teal;" ontouchmove="ThinkTank();" onmouseover="ThinkTank();"> 
    <b> Think Tank </b> <hr> 
	</div>

	<div>
        <select id="Birds">
            <option>Eagle</option>
            <option>Crow</option>
            <option>Sparrow</option>
            <option>Owl</option>
        </select>
        <button onclick="checkSelection()" ontouchstart="checkSelection()">Submit</button>
	</div>


	</body>
    </html>
