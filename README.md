# Design of a Standard Calculator

## AIM:

To design a web application for a standard calculator.

## DESIGN STEPS:

### Step 1:
Clone repository from github and create own django project with name calculation then django app with name calculator. 


### Step 2:
Then in settings.py in Allowed host keep '*' to allow every user and mention your app name in Installed apps.


### Step 3:
Create a templates inside the app folder name calculator inside it again create new folder with name calculator then inside it create new html file with name calculation.html.

### Step 4:
After writing all css and html code to calculation.html define your views in views.py and define path to your application in url_pattern in urls.py

### Step 5:
Then apply all migrations to your file and migrate it.Then run server and check whether the application is functioning well or not

### Step 6:

Validate the HTML and CSS code.

### Step 6:

Publish the website in the given URL.

## PROGRAM :
### HTML Code:
```
<!DOCTYPE HTML>
<html lang='en'>
    <head>
        <title>My Standard-Calculator</title>
        <style>
        .calc{
            width:600px;
            height:475px;
            margin-left:auto;
            margin-right:auto;
            background-color:gray;

        }
        #result{
            background-color:white;
            text-align:right;
        }
        .calc_title{
            text-align:center;
            
        }
        .size{
            padding:16px;
        }
        .color{
            color:red;
        }
        </style>
        <script>
        function calculate(args)
        {
            res = document.getElementById("result")
            expression = res.innerText;
            cmd = args.srcElement.innerText;
            if (cmd == "=")
            {
                expression = ""+eval(expression);
            }
            else if(cmd =="C"){
                expression=" ";
            }
            else{
               expression = expression +cmd;
            }
            res.innerText = expression;
            // alert("clicked")

        }
        </script>
    </head>
    <body>
        <div class="calc">
            <div class="calc_title">
               <h1>STANDARD CALCULATOR</h1>
            </div>
        <div id="result">0</div>
        <div class="size">
         <button onclick="calculate(event);" class="size">0</button>
         <button onclick="calculate(event);" class="size">1</button>
         <button onclick="calculate(event);" class="size">2</button>
         <button onclick="calculate(event);" class="size">+</button>
        </div>
        <div class="size">
         <button onclick="calculate(event);" class="size">3</button>
         <button onclick="calculate(event);" class="size">4</button>
         <button onclick="calculate(event);" class="size">5</button>
         <button onclick="calculate(event);" class="size">-</button>
        </div>
        <div class="size">
         <button onclick="calculate(event);" class="size">6</button>
         <button onclick="calculate(event);" class="size">7</button>
         <button onclick="calculate(event);" class="size">8</button>
         <button onclick="calculate(event);" class="size">*</button>
        </div>
         <div class="size">
         <button onclick="calculate(event);" class="size">9</button>
         <button onclick="calculate(event);" class="size">/</button>
         <button onclick="calculate(event);" class="size">C</button>
         <button onclick="calculate(event);" class="size">=</button>
        </div>
       </div>
    </body>
</html>
```
# Views.py Code:
```
from django.shortcuts import render

def calculation(request):
    return render(request, "calculation/calculation.html")
```
# Urls.py Code:
```
from django.contrib import admin
from django.urls import path
from calculation import views

urlpatterns = [
    path('admin/', admin.site.urls),
    path('calculation',views.calculation,name="calculation")
]
```
## OUTPUT:
# Input:
![input](./images/calculatorinput.png)
# Output:
![output](./images/calculatoroutput.png)
# HTML Validation:
![validation](./images/calculatorvalidation.png)

## Result:
 Thus the standard calculator is successfully executed

