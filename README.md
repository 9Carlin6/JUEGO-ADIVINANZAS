# JUEGO-ADIVINANZAS
Aprendiendo a unir HTML con JavaScript: Input, button, random, focus, value, While.

<meta charset="UTF-8"><br>
<h1><h3>JUEGO DE ADIVINACION.3</h3></h1>
<br><big>Piensa un numero del 1 al 10!</big></br>
<br><input/><br><br>
<button> Verificar </button>
<script>
        var piensaNum= Math.round(Math.random()*10);
        var input= document.querySelector("input");
        var intentos=3
        var conteo= 0
        input.focus();
    function verificar() {    
        if (conteo == intentos) {
            alert("CUMPLISTE TRES INTENTOS");
        }
        while(conteo < intentos) { 
            if (parseInt(input.value) == piensaNum) {
                alert("ADIVINASTE, FELICITACIONES!");
                alert("CUMPLISTE, fin del juego.");
                conteo = conteo + intentos++ //Detiene el bucle una vez haya ganado. Lo cual no se logra con break o con return.
            }
            else {
                alert("FALLASTE, te quedan " + (intentos - conteo - 1) + " intentos")
                conteo++;
                input.value="";
                input.focus();
                break;
                
            }   
        }
    }   
    var button =document.querySelector("button");
    button.onclick = verificar;
</script>
