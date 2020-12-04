# displayMessage-alertlike
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>alert replacement</title>
    </head>
    <body>
      
        

       
        <button id="click">Display message box</button>
        
        <style>
            
            .msgBox  {
                font-size: 16px;
                margin: 0 auto;
                border: solid seagreen;
                border-radius: 10px;
                width: 400px;
                height: 100px;
                background-color: linen;

            }
            
        </style>

        <script>

            
            
            const btn = document.querySelector('#click');
            /* btn.onclick = displayMessage; ==> after onclick if using function name never use () 'parentheses are called function ovocation operator' only use them when you                 wanto to run the function immediately!*/
            /*instead of above line */
            btn.onclick = function(){
              displayMessage('warning','Woo, this is a different message!');
            };

          
            function displayMessage(msgType, msgText){
              const html = document.querySelector('html');
                
              const panel = document.createElement('div');
              panel.setAttribute('class', 'msgBox');  /*we mset attribute to be easier to style it in CSS*/
              html.appendChild(panel);

              const msg = document.createElement('p');
              panel.appendChild(msg);
              msg.textContent = msgText;

              const closeButton = document.createElement('button');
              /*we create it here to append it to panel,if write it in html it appear any where but now it belongs to panal*/                                                                                
              closeButton.textContent = 'x';
              panel.appendChild(closeButton);
                

              closeButton.onclick = function(){  /* anonumous function is not run immediately,as it is inside th function scope*/
                html.removeChild(panel);
                }

                if(msgType === 'warning'){
                  msg.style.backgroundImage = 'url(./warning.png)';
                  panel.style.backgroundColor = 'pink';  
                } else if(msgType === 'chat'){
                  msg.style.backgroundImage = 'url(./chat(2).png)'; 
                  panel.style.backgroundColor = 'lightblue';
                } else{
                  msg.style.paddingLeft = '20px';  
                }


                }
            
           
           
        </script>
    </body>



</html>
