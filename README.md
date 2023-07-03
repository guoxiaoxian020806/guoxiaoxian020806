<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>好朋友认识时间记录</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f4f4f4;
    }
    
    .container {
      max-width: 500px;
      margin: 0 auto;
      padding: 20px;
      background-color: #fff;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    }
    
    h1 {
      text-align: center;
      margin: 0 0 20px;
    }
    
    .friend-form {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 10px;
    }
    
    .friend-form input[type="text"] {
      flex-grow: 1;
      padding: 5px;
    }
    
    .friend-form button {
      margin-left: 10px;
      padding: 5px 10px;
      background-color: #4d90fe;
      color: #fff;
      text-decoration: none;
      border-radius: 5px;
      cursor: pointer;
    }
    
    .friend {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 10px;
      padding: 10px;
      background-color: #f9f9f9;
    }
    
    .friend .name {
      font-weight: bold;
    }
    
    .friend .date {
      color: #999;
      font-size: 14px;
    }
    
    .friend .delete-btn {
      background-color: #ff0000;
    }
  </style>
  <script>
    // 添加好朋友
    function addFriend() {
      var nameInput = document.getElementById("name");
      var dateInput = document.getElementById("date");
      
      var name = nameInput.value;
      var date = dateInput.value;
      
      if (name !== "" && date !== "") {
        var friend = document.createElement("div");
        friend.classList.add("friend");
        friend.innerHTML = '<div class="name">' + name + '</div><div class="date">' + date + '</div><button class="delete-btn" onclick="deleteFriend(this)">删除</button>';
        document.getElementById("friend-list").appendChild(friend);
        
        nameInput.value = "";
        dateInput.value = "";
      }
    }
    
    // 删除好朋友
    function deleteFriend(btn) {
      var friend = btn.parentNode;
      friend.parentNode.removeChild(friend);
    }
  </script>
</head>
<body>
  <div class="container">
    <h1>好朋友认识时间记录</h1>
    
    <div class="friend-form">
      <input type="text" id="name" placeholder="输入好朋友的名字">
      <input type="text" id="date" placeholder="输入认识的日期">
      <button onclick="addFriend()">添加好朋友</button>
    </div>
    
    <div id="friend-list"></div>
  </div>
</body>
</html>
