//onlineshope.html

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="onlineshop.css">
</head>
<body>
    <div class="nav">
        <a class="a" id="home" href="onlineshop.html">Home</a>
        <a class="a" id="about" href="about.html">About</a>
        <a class="a" id="login" href="login.html">Login</a>
    </div><br><br>
    <img src="D:\off.jpg" alt="offer" style="margin-left: 10px;">
    <img src="D:\off1.jpg" alt="offer" style="height: 51%; width: 51%;"><br><br>
    <h1 style="margin-left: 25%;">We have arranged everything you need to sell electronics online</h1>
    <img src="D:\off2.jpeg" alt="offer" style="margin-left: 5%; width: 40%; height: 40%;">
    <img src="D:\off3.jpg" alt="offer" style="margin-left: 10%; width: 40%; height: 40%;"><br><br>
    <div style="border: 3px solid; margin-left: 35%; text-align: center; height: 200px; width: 500px;">
      <h1>Product List</h1> 
		  Search Product Here: <input type="text" id="search" placeholder="Product Name"><br><br>
		  <button style="height: 40px; width: 100px; font-size: 20px; background-color: palevioletred;">search</button>
    </div>
    <table id="pro" border="2">
      <tr>
        <th>Product Name</th>
        <th>Product Price</th>
        <th>Product Image</th>
      </tr>
    </table>
    <a href=""></a>
    <script src="https://code.jquery.com/jquery-3.7.1.min.js" integrity="sha256-/JqT3SQfawRcv/BIHPThkBvs0OEvtFFmqPF/lYI/Cxo=" crossorigin="anonymous"></script>
    <script>
        $(document).ready(function(){
             $.getJSON("product.json" , function(obj){
              var product = "";
              $.each(obj , function(key , value){
                product += '<tr>' ;
                product += '<td style="font-size: x-large;">' + value.pname + '</td>' ;
                product += '<td style="font-size: x-large;">' + value.price +'</td>';
                product += '<td><img src="'+ value.pimg +'" height="200" width="200"></td>'; 
							  product += '<td><button style="font-size: x-large;"><a href="phone.html">Buy</a></button></td>'; 
                product += '</tr>' ;
            });
            $("#pro").html(product); 
          });
          $("#search").keyup(function(){
            var a = $("#search").val() ;
            $.getJSON("product.json" , function(obj){
              var product = "";
              $.each(obj , function(key , value){
                if (a == value.pname) {
                  product += '<tr>' ;
                  product += '<td style="font-size: x-large;">' + value.pname + '</td>' ;
                  product += '<td style="font-size: x-large;">' + value.price +'</td>';
                  product += '<td><img src="'+ value.pimg +'" height="200" width="200"></td>'; 
							    product += '<td><button style="font-size: x-large;">Buy</button></td>'; 
                  product += '</tr>' ;
                }
                else if (a == null || a == "") {
                  product += '<tr>' ;
                  product += '<td style="font-size: x-large;">' + value.pname + '</td>' ;
                  product += '<td style="font-size: x-large;">' + value.price +'</td>';
                  product += '<td><img src="'+ value.pimg +'" height="200" width="200"></td>'; 
							    product += '<td><button style="font-size: x-large;">Buy</button></td>'; 
                  product += '</tr>' ;
                }
            });
            $("#pro").html(product); 
          });
          });
        });
    </script>
</body>
</html>

//onlineshope.css

.nav {
    overflow: hidden;
    text-align: center;
    background-color: black;
    font-size: 20px;
    height: 35px ;
    padding: 1px;
}
.a {
    color: white;
}
#home {
    margin-left: 1%;
}
#about {
    margin-left: 20px;
}
#login {
    margin-left: 20px;
}
.p1 {
    border-radius: 3px solid;
    box-shadow: 0 10px 20px 0px rgba(65, 59, 59, 0.911);
    height: 40%;
    width: 35%;
    text-align: center;
    padding: 15px;
    margin-left: 32%;
    padding-top: 30px;
    background-color: blue;
    color: aliceblue;
    border: 5px solid black;
}
.p2 {
    border-radius: 3px solid;
    box-shadow: 0 10px 20px 0px rgba(65, 59, 59, 0.911);
    height: 40%;
    width: 35%;
    text-align: center;
    padding: 15px;
    margin-left: 32%;
    padding-top: 30px;
    background-color: blue;
    color: aliceblue;
    border: 5px solid black;
}
.p3 {
    border-radius: 3px solid;
    box-shadow: 0 10px 20px 0px rgba(65, 59, 59, 0.911);
    height: 40%;
    width: 35%;
    text-align: center;
    padding: 15px;
    margin-left: 32%;
    padding-top: 30px;
    background-color: blue;
    color: aliceblue;
    border: 5px solid black;
}
.box {
    font-size: x-large;
    border-radius: 3px solid;
    box-shadow: 0 10px 20px 0px rgba(65, 59, 59, 0.911);
    height: 70%;
    width: 60%;
    text-align: center;
    padding: 15px;
    margin-left: 20%;
    padding-top: 30px;
    margin-top: 30px;
    background-color: rgb(43, 83, 226);
}
body {
    background-color: rgba(16, 113, 126, 0.474);
}
.logo {
    padding: 50px;
    border-radius: 10px;
    box-shadow: 0 10px 20px 0px rgba(0, 0, 0, 0.15);
    background-color: black;
    height: 400px;
    overflow: hidden;
    margin-top: 30px;
}
.facebook {
    margin-left: 80%;
}
.insta {
    margin-left: 10px;
}
.youtube {
    margin-left: 10px;
}
tbody td {
    text-align: left;
    padding-left: 30px;
    padding-right: 20px;
}
th {
    padding-left: 50px;
    padding-right: 50px;
}
#map {
    margin-left: 31%;
}
#pro {
    width: 100%;
    text-align: center;
}

//login.html

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="onlineshop.css">
</head>
<body>
    <div class="nav">
        <a class="a" id="home" href="onlineshop.html">Home</a>
        <a class="a" id="about" href="about.html">About</a>
        <a class="a" id="login" href="login.html">Login</a>
    </div><br><br>
    <form method="post">
        <div class="box">
        <div class="heading">
            <h3>login</h3>
            <p>Sign in with your username and password</p>
        </div>
        <div class="form">
            <label for="email">Your emailadd</label>
            <input style="border: 3px solid;" type="email" placeholder="Enter Email" name="email" id="LoginEmail">
            <br><br>
            <label for="psw">Your password</label>
            <input style="border: 3px solid;" type="password" placeholder="Enter Password" name="psw" id="LoginPass">
            <br><br>
             <button style="border: 3px solid;" type="submit" onclick="LoginValid()">Login</button>
        </div>
        <h5>If you are not a member of this site!</h5>
        <h5>so sign up here!</h5>
        <button><a href="3.html">sing up</a></button>
        </div>
    </form><br><br>
    <div class="logo">
        <table style=" color: white;">
          <tr id="a1">
            <th>Resources</th>
            <th>Solution</th>
            <th>About us</th>
            <th>Ranking</th>
            <th>Data</th>
          </tr>
          <tr id="a2">
            <td>Blog</td>
            <td>Digital Research Intelligence</td>
            <td>Company</td>
            <td>Top Websites</td>
            <td>Our Data</td>
          </tr>
          <tr id="a3">
            <td>Reports</td>
            <td>Digital Marketing Intelligence</td>
            <td>Customers</td>
            <td>Top Android Apps</td>
            <td>Verify Your Website</td>
          <tr id="a4">
            <td>Events</td>
            <td>Shopper Intelligence</td>
            <td>Partners</td>
            <td>Mobile vs. Desktop</td>
            <td>Customers Data</td>
          </tr>
          <tr id="a5">
            <td>Knowledge Center</td>
            <td>Sales Intelligence</td>
            <td>Pricing</td>
            <td>Top Search Engines</td>
            <td>Browser Extension</td>
          </tr>
          <tr id="a6">
            <td>Insights</td>
            <td>Advisory Services</td>
            <td>Management</td>
            <td>Top Browsers</td>
            <td>Company Data</td>
          </tr>
        </table>  
      <div class="sym">
      <img class="facebook" src="D:\facebook.png" alt="facebook" width="50px" height="50px">
      <img class="insta" src="D:\insta.png" alt="instagram" width="50px" height="50px">
      <img class="youtube" src="D:\youtube.png" alt="youtube" width="50px" height="50px">
      </div>
      </div>
</body>
</html>

//about.html

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="onlineshop.css">
</head>
<body>
    <div class="nav">
        <a class="a" id="home" href="onlineshop.html">Home</a>
        <a class="a" id="about" href="about.html">About</a>
        <a class="a" id="login" href="login.html">Login</a>
    </div><br><br>
    <div class="p1">
        If you're looking to set up a website with a beautiful, clean and flat design style, you'll need to check out the Electronics Store Layout Pack. 
        This modern layout pack beautifully combines touches of colors with clean product photography and well-thought-out typography!
    </div><br><br>
    <div class="p2">
        Electronics have a profound impact on various aspects of modern society and culture, such as communication, entertainment, 
        education, health care, industry, and security. 
    </div><br><br>
    <div class="p3">
        Electronics is a scientific and engineering discipline that studies and applies the principles of physics to design, create,
         and operate devices that manipulate electrons and other electrically charged particles.
    </div><br>
    <div id="map">
    <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d29765.63402522429!2d72.77873610866173!3d21.16416480320308!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3be05378c5475ea5%3A0x58deb914fc914962!2sVIJAY%20SALES%20-%20VESU!5e0!3m2!1sen!2sin!4v1707315987997!5m2!1sen!2sin" 
    width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
    </div>
    <div class="logo">
        <table style=" color: white;">
          <tr id="a1">
            <th>Resources</th>
            <th>Solution</th>
            <th>About us</th>
            <th>Ranking</th>
            <th>Data</th>
          </tr>
          <tr id="a2">
            <td>Blog</td>
            <td>Digital Research Intelligence</td>
            <td>Company</td>
            <td>Top Websites</td>
            <td>Our Data</td>
          </tr>
          <tr id="a3">
            <td>Reports</td>
            <td>Digital Marketing Intelligence</td>
            <td>Customers</td>
            <td>Top Android Apps</td>
            <td>Verify Your Website</td>
          <tr id="a4">
            <td>Events</td>
            <td>Shopper Intelligence</td>
            <td>Partners</td>
            <td>Mobile vs. Desktop</td>
            <td>Customers Data</td>
          </tr>
          <tr id="a5">
            <td>Knowledge Center</td>
            <td>Sales Intelligence</td>
            <td>Pricing</td>
            <td>Top Search Engines</td>
            <td>Browser Extension</td>
          </tr>
          <tr id="a6">
            <td>Insights</td>
            <td>Advisory Services</td>
            <td>Management</td>
            <td>Top Browsers</td>
            <td>Company Data</td>
          </tr>
        </table>  
      <div class="sym">
      <img class="facebook" src="D:\facebook.png" alt="facebook" width="50px" height="50px">
      <img class="insta" src="D:\insta.png" alt="instagram" width="50px" height="50px">
      <img class="youtube" src="D:\youtube.png" alt="youtube" width="50px" height="50px">
      </div>
      </div>
</body>
</html>

//product.json

[
    {"pname" : "Phone" , "price" : 25000 , "pimg" : "phone1.webp"} ,
    {"pname" : "Phone" , "price" : 19999 , "pimg" : "phone2.webp"} ,
    {"pname" : "Phone" , "price" : 20000 , "pimg" : "phone3.webp"} ,
    {"pname" : "Phone" , "price" : 130999 , "pimg" : "phone4.jpg"} ,
    {"pname" : "Freeze" , "price" : 61499 , "pimg" : "freeze1.webp"} ,
    {"pname" : "Freeze" , "price" : 40599 , "pimg" : "freeze2.webp"} ,
    {"pname" : "Freeze" , "price" : 80999 , "pimg" : "freeze3.jpg"} ,
    {"pname" : "Smart Watch" , "price" : 2650 , "pimg" : "watch1.jpg"} ,
    {"pname" : "Smart Watch" , "price" : 4500 , "pimg" : "watch2.jpg"} ,
    {"pname" : "Budes" , "price" : 5000 , "pimg" : "budes1.webp"} ,
    {"pname" : "Bluetooth Speaker" , "price" : 7000 , "pimg" : "budes2.png"} ,
    {"pname" : "TV" , "price" : 39999 , "pimg" : "tv1.jpg"} ,
    {"pname" : "TV" , "price" : 30000 , "pimg" : "tv2.webp"} ,
    {"pname" : "TV" , "price" : 50999 , "pimg" : "tv3.jpg"} ,
    {"pname" : "Washing Machine" , "price" : 16999 , "pimg" : "whashingmachine1.webp"} ,
    {"pname" : "Washing Machine" , "price" : 25000 , "pimg" : "whashingmachine2.jpg"} 
]

//phone.html
//to open a item with new page

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        #demo {
            display: flex;
            padding: 20px;
        }
        #mobile {
            margin-left: 5%;
            height: 150%;
            width: 100%;
            text-align: left;
            padding: 50px;
        }
    </style>
</head>
<body style="background-color:  rgba(16, 113, 126, 0.474);">
    <div id="demo">
        <img style="width: 60%;" height="70%" src="phone2.webp" alt="Mobile Phone">
        <div id="mobile">
            <h1 style="color: blue;">Realme 9i 5G Soulful Black</h1>
            <h3>6GB RAM Gsm</h3>
            <h3>128GB</h3>
            <h3>Unlocked Phone</h3>
            <h3>MediaTek MT6833P</h3>
            <h3>Dimensity 810 50MP</h3>
            <h3 style="color: red;">EMI Starts @ ₹1068.49/ Month</h3>
            <h3 style="color: red;">₹19999.00  6% Off</h3>
        </div>
    </div>
    <h1 style="margin-left: 37%; font-size: xx-large; color: red;">Order Now!</h1>
    <button style="margin-left: 39%; height: 50px ; width: 100px; font-size: 20px; color: blue;">Buy</button>
</body>
</html>
