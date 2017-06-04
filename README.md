	<!DOCTYPE html> 
	<html> 
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
        
        #TimedQuiz { 
            top:160px; left:330px; 						
          position:absolute; font-size:18px; 
        	font-family:arial; background-color:#ffffff;
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
       
         Countdown();
  	function Countdown() {
     	// Loop Countdown() - every 1000 milliseconds = 1 second.   
      	var timer = setTimeout(Countdown, 1000);
      
    	// Control the Output in the "clock" element  
    	var seconds = document.getElementById('clock').innerHTML;
    	// Decrement (decrease) the Output in the "clock" element by one.
    	seconds--;
    
    	// Display the amounts left on the "clock" element.
    	var message = document.getElementById('clock');
    	message.innerHTML = seconds;
      
    	// If the user inputs the correct answer, stop (clear) the timer.  
    	var input = document.getElementById("answer");
      	if (input.value =="fruit") {
          message.innerHTML = "Correct!"; 
          clearInterval(timer);
          input.style.backgroundColor="#00ff00"; 
          input.style.color="#ffffff";
      }
      
       if (input.value =="vegetable") {
          alert("Incorrect."); 
          input.style.backgroundColor="#ffffff"; 
          input.style.color="#ff0000";
      }
      
      if (seconds==0) { 
          message.innerHTML = "TIME'S UP!"; 
          clearInterval(timer);
          input.style.backgroundColor="#ff0000"; 
          input.style.color="#ff0000";}
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

    <div id="TANK" style="background-color:#ff6; width:300px; height:350px; color:teal;"> 
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

    <div id="TimedQuiz">
    Time Left:
	<b id="clock" style="color:#0000ff;">10</b> <br>
	<b id="question" style="color:#ff0000;"> Is an Apple a "fruit" or "vegetable"? </b> <br>
	<input id="answer" />
    	</div>

	</body>
	</html>
