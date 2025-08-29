# IMC
Calculador IMC INICIANTE
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>IMC</title>
</head>
<style>
    body {
        font-family: Arial, "Helvetica Neue", Helvetica, sans-serif;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        height: 100vh;
        background-color: #f0f0f0;
        
    }
    div {
        background-color: #fff;
        padding: 20px 30px;
        border-radius: 10px;
        box-shadow: 0 4px 10 px rgba(0, 0, 0, 0);
    }
    input {
        padding: 10px;
        margin: 5px;
        width: 150px;
        border-radius: 5px;
        border: 1px solid #ccc ;
    }

    button {
        padding: 10px 20px;
        border-radius: 5px;
        border: none;
        background-color: rgb(102, 128, 65);
        color: white;
        cursor: pointer;
        font-weight: bold;
    }

    button:hover{
        background-color: red;
    }  
    #resultado {
        font-weight: bold;
        font-size: 1.2em;
        color:#333;

    }  
</style>
<body>
    
    <div>
        <h1>Calculadora IMC</h1>

        <input type="number" id="peso" placeholder="Peso">
        <input type="number" id="altura" placeholder="Altura">
    </div>

    <div>
        <button id="calcular">Calcular</button>
        
    </div>

    <div>
        <p>Resultado: <span id="resultado"></span></p>
    </div>

    <script>
        const p = document.getElementById("peso");
        const h = document.getElementById("altura");
        const btnCalcular = document.getElementById("calcular");
        const resultado = document.getElementById("resultado");

        btnCalcular.addEventListener("click" , () => {
            if (p.value ==="" || h.value ===""){
                alert("Preencha os dois Numeros ")
                return; //para nao continuar a conta
            }

            const peso = Number(p.value);
            const altura = Number(h.value);



            

            const calcular = peso / (altura * altura);
            let classificacao = ""
            
        if (calcular < 18.5 ) {
            
            classificacao = "esta abaixo do peso"
        }else if ( calcular >= 18.5 && calcular < 25 ) {
           
            classificacao = "esta no peso normal"
        }else if(calcular >= 25 && calcular < 30) {
             
            classificacao = "esta sobrepeso"
        }else if (calcular >=30 && calcular <35) {
            
            classificacao = "esta com Obesidade grau I"
        } else if (calcular >= 35 && calcular < 40) {
            
            classificacao = "esta com Obesidade grau II (ou severa)"
        }else if(calcular >= 40 ) {
              
            classificacao ="esta com Obesidade grau III (ou morbida)"

        }
        resultado.textContent = `${calcular.toFixed(2)} (${classificacao})`;
        });
        
    </script>
</body>
</html>
