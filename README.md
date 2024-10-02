# Calculator
This is basically made with html, Css and Script.
<!DOCTYPE html>  
<html lang="en">  
<head>  
    <meta charset="UTF-8">  
    <meta name="viewport" content="width=device-width, initial-scale=1.0">  
    <title>Calculator</title>  
    <style>  
        body {  
            font-family: Arial, sans-serif;  
            background-color: #f0f0f0;  
        }  
        
        .calculator {  
            width: 400px;  
            margin: 60px auto;  
            background-color: #fff;  
            padding: 20px;  
            border: 1px solid #ddd;  
            border-radius: 10px;  
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);  
        }  
        
        #display {  
            width: 100%;  
            height: 80px;  
            margin-bottom: 10px;  
            padding: 2px;  
            font-size: 70px;  
            text-align: right;  
            border: 1px solid #ccc;  
        }  
        
        .button {  
            width: 50px;  
            height: 50px;  
            margin: 5px;  
            padding: 10px;  
            font-size: 20px;  
            border: none;  
            border-radius: 5px;  
            cursor: pointer;  
        }  
        
        .button:hover {  
            background-color: #ccc;  
        }  
        
        #clear {  
            background-color: #ff9800;  
            color: #fff;  
        }  
        
        #delete {  
            background-color: #ff9800;  
            color: #fff;  
        }  
        
        #percent {  
            background-color: #03a9f4;  
            color: #fff;  
        }  
        
        #divide {  
            background-color: #03a9f4;  
            color: #fff;  
        }  
        
        #multiply {  
            background-color: #03a9f4;  
            color: #fff;  
        }  
        
        #subtract {  
            background-color: #03a9f4;  
            color: #fff;  
        }  
        
        #add {  
            background-color: #03a9f4;  
            color: #fff;  
        }  
        
        #equals {  
            background-color: #00c853;  
            color: #fff;  
        }  
        
        .row {  
            display: flex;  
            justify-content: space-between;  
            margin-bottom: 10px;  
        }  
    </style>  
</head>  
<body>  
    <div class="calculator">  
        <input type="text" id="display" disabled>  
        <div class="row">  
            <button class="button" id="clear">C</button>  
            <button class="button" id="delete">DEL</button>  
            <button class="button" id="percent">%</button>  
            <button class="button" id="divide">/</button>  
        </div>  
        <div class="row">  
            <button class="button" id="seven">7</button>  
            <button class="button" id="eight">8</button>  
            <button class="button" id="nine">9</button>  
            <button class="button" id="multiply">*</button>  
        </div>  
        <div class="row">  
            <button class="button" id="four">4</button>  
            <button class="button" id="five">5</button>  
            <button class="button" id="six">6</button>  
            <button class="button" id="subtract">-</button>  
        </div>  
        <div class="row">  
            <button class="button" id="one">1</button>  
            <button class="button" id="two">2</button>  
            <button class="button" id="three">3</button>  
            <button class="button" id="add">+</button>  
        </div>  
        <div class="row">  
            <button class="button" id="zero">0</button>  
            <button class="button" id="decimal">.</button>  
            <button class="button" id="equals">=</button>  
        </div>  
    </div>  

    <script>  
        let display = document.getElementById('display');  
        let buttons = document.querySelectorAll('.button');  
        let input = '';  
        let total = 0;  

        buttons.forEach(button => {  
            button.addEventListener('click', () => {  
                switch (button.id) {  
                    case 'clear':  
                        input = '';  
                        display.value = '';  
                        break;  
                    case 'delete':  
                        input = input.slice(0, -1);  
                        display.value = input;  
                        break;  
                    case 'equals':  
                        try {  
                            total = eval(input);  
                            display.value = total;  
                            input = total.toString();  
                        } catch (e) {  
                            display.value = 'Error';  
                            input = '';  
                        }  
                        break;  
                    default:  
                        input += button.textContent;  
                        display.value = input;  
                }  
            });  
        });  
    </script>  
</body>  
</html>
