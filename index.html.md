<!DOCTYPE html>  
<html lang="mn">  
<head>  
<meta charset="UTF-8">  
<meta name="viewport" content="width=device-width, initial-scale=1">  
<title>Дүнгийн мэдээлэл (Demo)</title>  
  
<style>  
body {  
    margin: 0;  
    font-family: system-ui, Arial;  
    background: #f4f6f9;  
    color: #111;  
}  
.header {  
    background: #fff;  
    padding: 12px;  
    display: flex;  
    align-items: center;  
    border-bottom: 1px solid #ddd;  
}  
.header img {  
    height: 40px;  
    margin-right: 10px;  
}  
.container {  
    padding: 15px;  
}  
.card {  
    background: #fff;  
    border-radius: 10px;  
    padding: 15px;  
    margin-bottom: 15px;  
}  
.title {  
    font-weight: 600;  
    font-size: 18px;  
    margin-bottom: 10px;  
}  
button {  
    background: #2563eb;  
    color: white;  
    border: none;  
    padding: 10px;  
    border-radius: 8px;  
    width: 100%;  
    font-size: 15px;  
}  
input {  
    width: 100%;  
    padding: 10px;  
    border-radius: 8px;  
    border: 1px solid #ccc;  
    margin-top: 8px;  
}  
table {  
    width: 100%;  
    border-collapse: collapse;  
}  
th, td {  
    border-bottom: 1px solid #ddd;  
    padding: 8px;  
    text-align: left;  
    font-size: 14px;  
}  
.edit {  
    color: #2563eb;  
    cursor: pointer;  
}  
.small {  
    font-size: 13px;  
    color: #555;  
}  
</style>  
</head>  
  
<body>  
  
<div class="header">  
    <img src="https://upload.wikimedia.org/wikipedia/en/5/57/Mongolian_University_of_Science_and_Technology_logo.png">  
    <strong>МУИС Технологийн Их Сургууль (Demo)</strong>  
</div>  
  
<div class="container">  
  
<div class="card">  
    <div class="title">Дүнгийн мэдээлэл</div>  
    <div class="small" id="date"></div>  
</div>  
  
<div class="card">  
    <div class="title">Дүнгийн хуудсыг хэвлэх</div>  
    <button onclick="alert('Demo only')">Дүнгийн мэдээлэл татах</button>  
</div>  
  
<div class="card">  
    <div class="title">E-mail хаягаар илгээх</div>  
    <input id="email" placeholder="E-mail хаяг">  
    <button onclick="saveEmail()">Илгээх</button>  
</div>  
  
<div class="card">  
    <div class="title">Дүнгийн мэдээлэл</div>  
    <table>  
        <tr>  
            <th>Хичээлийн нэр</th>  
            <th>Кредит</th>  
            <th>Б.Оноо</th>  
            <th>Шал.Оноо</th>  
        </tr>  
        <tr>  
            <td>Физик I</td>  
            <td>3</td>  
            <td contenteditable="true" oninput="saveGrades()">0</td>  
            <td contenteditable="true" oninput="saveGrades()">0</td>  
        </tr>  
        <tr>  
            <td>Математик I</td>  
            <td>3</td>  
            <td contenteditable="true" oninput="saveGrades()">0</td>  
            <td contenteditable="true" oninput="saveGrades()">0</td>  
        </tr>  
    </table>  
</div>  
  
</div>  
  
<script>  
document.getElementById("date").innerText =  
    new Date().toLocaleDateString("mn-MN");  
  
function saveEmail() {  
    localStorage.setItem("demoEmail", email.value);  
    alert("Demo: E-mail хадгалагдлаа");  
}  
  
function saveGrades() {  
    localStorage.setItem("grades",  
        document.querySelector("table").innerHTML);  
}  
  
if (localStorage.getItem("grades")) {  
    document.querySelector("table").innerHTML =  
        localStorage.getItem("grades");  
}  
  
email.value = localStorage.getItem("demoEmail") || "";  
</script>  
  
</body>  
</html>  
