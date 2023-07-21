# mytodo.Abhi
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Todo list </title>
    <style>
       .container {
            width:100%;
            min-height: 100vh;
            background:linear-gradient(135deg,#238283,#4e085f);
            padding: 10px;
        }
        .todo-list{
            width:100%;
            max-width: 100vh;
            background: #fff;
            margin:100px auto 20px;
            padding: 40px 30px 70px;
            border-radius: 10px;
        }
        ul {
  margin: 0;
  padding: 0;
}

/* Style the list items */
ul li {
  cursor: pointer;
  position: relative;
  padding: 12px 8px 12px 40px;
  list-style-type: none;
  background: #eee;
  font-size: 18px;
  transition: 0.2s;
  
  /* make the list items unselectable */
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

/* Set all odd list items to a different color (zebra-stripes) */
ul li:nth-child(odd) {
  background: #d4ced3;
}

/* Darker background-color on hover */
ul li:hover {
    background:linear-gradient(135deg,#238283,#4e085f);
}

/* When clicked on, add a background color and strike out text */
ul li.checked {
  background: #edeef0;
  color: #121212;
  text-decoration: line-through;
}

/* Add a "checked" mark when clicked on */
ul li.checked::before {
  content: '';
  position: absolute;
  border-color: #fff;
  border-style: solid;
  border-width: 0 2px 2px 0;
  top: 10px;
  left: 16px;
  transform: rotate(45deg);
  height: 15px;
  width: 7px;
}

        .close {
        position: absolute;
        right: 0;
        top: 0;
        padding: 12px 16px 12px 16px;
}

        .close:hover {
         background-color: #f90516;
            color: white;
}
        
            .todo-list h2{
                color:#002765;
                display:inline;
                align-item:center;
                margin-bottom: 20px;
            }
            .todo-list h2 img{
                width:30px;
                margin-left:10px;
                
            }
            .row{
                display:flex;
                align-item:center;
                justify-content: space-between;
                background:#edeef0;
                border-radius:30px;
                padding-left:20px;

            }
            input{
                flex:1;
                border: none;
                outline:none;
                background: transparent;
                padding: 10px;
                font-weight:14px;

            }
            .button {
            display: inline-block;
            padding: 15px 25px;
            font-size: 25px;
            cursor: pointer;
           text-align: center;
             text-decoration: none;
             outline: none;
             color: #fff;
             background-color: #452ca8;
                border: none;
            border-radius: 15px;
             box-shadow: 0 9px #999;
}
            .button:hover {background-color: #452ca8}

            .button:active {
            background-color: #452ca8;
            box-shadow: 0 5px #666;
            transform: translateY(4px);
}
            
        
    </style>
    <link rel="stylesheet" href="abhi.css">


    
</head>
<body>
    <div class="container">
<div class="todo-list">
    <h2>To-Do list <img src="https://www.bing.com/ck/a?!&&p=028fe8c17e1ee13cJmltdHM9MTY4NzIxOTIwMCZpZ3VpZD0wYjY1YzcxOC1kMGFlLTZmNTAtMTY0ZC1kNTM3ZDFhODZlNGEmaW5zaWQ9NTU5Nw&ptn=3&hsh=3&fclid=0b65c718-d0ae-6f50-164d-d537d1a86e4a&u=a1L2ltYWdlcy9zZWFyY2g_cT1saXN0IGltYWdlJkZPUk09SVFGUkJBJmlkPTBFOTlFQzcyRUY3MTRGNzRDNzI3RjhERkEwQzk4NDRFMkQ3ODA4NDc&ntb=1"></h2>
 <div class ="row">
    <input type="text"  id="input-box" placeholder="add your text">
    <span onclick="newElement()"
        class=button>Add
    </span>
 </div>
</div>

<ul id="myUL">
    
</ul>
</div>
    <script>
        var myNodelist = document.getElementsByTagName("LI");
var i;
for (i = 0; i < myNodelist.length; i++) {
  var span = document.createElement("SPAN");
  var txt = document.createTextNode("\u00D7");
  span.className = "close";
  span.appendChild(txt);
  myNodelist[i].appendChild(span);
}

// Click on a close button to hide the current list item
var close = document.getElementsByClassName("close");
var i;
for (i = 0; i < close.length; i++) {
  close[i].onclick = function() {
    var div = this.parentElement;
    div.style.display = "none";
  }
}

// Add a "checked" symbol when clicking on a list item
var list = document.querySelector('ul');
list.addEventListener('click', function(ev) {
  if (ev.target.tagName === 'LI') {
    ev.target.classList.toggle('checked');
  }
}, false);
       
    function newElement() {
  var li = document.createElement("li");
  var inputValue = document.getElementById("input-box").value;
  var t = document.createTextNode(inputValue);
  li.appendChild(t);
  if (inputValue === '') {
    alert("You must write something!");
  } else {
    document.getElementById("myUL").appendChild(li);
  }
  document.getElementById("input-box").value = "";

  var span = document.createElement("SPAN");
  var txt = document.createTextNode("\u00D7");
  span.className = "close";
  span.appendChild(txt);
  li.appendChild(span);

  for (i = 0; i < close.length; i++) {
    close[i].onclick = function() {
      var div = this.parentElement;
      div.style.display = "none";
    }
  }
}
</script>
</body>
</html>
