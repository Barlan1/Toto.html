# Todo.html
 <!DOCTYPE html>
<html lang="en">
<meta charset="UTF-8" >
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<head><title>To do list</title>

  <style>
   
    .completed{
        text-decoration: line-through;color:gray;
        background: #f0f0f0;
    }
 body
   {
      font-family: Arial, sans-serif;
      background: #f4f6f8;
      display: flex;
      justify-content: center;
      align-items: flex-start;
      min-height: 100vh;
      padding: 30px;
    }
    .container{
      background: white;
      padding: 20px 30px;
      border-radius: 10px;
      box-shadow: 0 4px 8px rgba(0,0,0,0.1);
      width: 350px;
    }
   
    h2
   {
      text-align: center;
      margin-bottom: 20px;
      color: #333;
    }
    
input 
   {
      width: 70%;
      padding: 10px;
      border: 1px solid #ddd;
      border-radius: 5px;
      outline: none;
     }

    button
   {
      padding: 10px 15px;
      margin-left: 5px;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      font-size: 14px;
    }
   
    button:hover
   {
      opacity: 0.9;
    }
    .btn
   {
      background-color: #4CAF50;
      color: white;
      font-size: 14px;
      font-weight: bold;
    }
    .doneBtn
   {
      background-color: rgb(243, 175, 85);
     padding: 8px;
     color: white;
     font-weight: bold;
     border-radius: 12px;
    }
    .removeBtn
   {
     background-color: rgb(32, 149, 228);
     padding: 8px;
     color:white;
     font-weight: bold;
     border-radius: 12px;
     
    }

    ul 
   {
      list-style: none;
      padding: 0;
      margin-top: 20px;
    }
    li
   {
      display: flex;
      padding: 10px;
      background: #fafafa;
      justify-content: space-between;
      margin-bottom: 8px;
      border-radius: 5px;
      border: 1px solid #eee;
      align-items: center;
    }
   
  </style>
</head>
<body>
 
<div class="container"> 
<h2>My Todo list</h2>
<input id="inputData" type="text">
<button class="btn" type="button" onclick="addTask()">AddTask</button>
<ul id="myList"></ul>
</div>
 
<Script>
  function addTask(){

    let input= document.getElementById("inputData")
    let text= input.value.trim();
    if( text === "") {alert("please enter task"); return;};
     

    let li= document.createElement("li");

     li.innerHTML= text;  //insert text to list
     
    //completeButton
    let completeButton=document.createElement("button");
    completeButton.innerHTML="done";
    completeButton.classList.add("doneBtn");
    completeButton.addEventListener("click", function(){
      li.classList.toggle("completed");
    });

     //delete button
    let deleteButton=document.createElement("button");
    deleteButton.innerHTML="Remove"; //naming button
    deleteButton.classList.add("removeBtn");
    deleteButton.addEventListener("click",function(){
      li.remove();   
    });
    
    //append button to list li
     li.append(completeButton)
     li.append(deleteButton); //add to list
    document.getElementById("myList").append(li);

    input.value="";  //clear input
}

document.getElementById("inputData").addEventListener("keydown",function(event){
  if(event.key ==="Enter"){
  addTask()
}
});
</Script>


</body>
</html>
