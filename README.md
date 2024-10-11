# Leia me sp cheat

<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Botão de Copiar no GitHub Pages</title>
</head>
<body>
    <h1>Cheat Leia-me</h1>
    <p>Abaixo está o código que pode ser copiado com um clique no botão:</p>
    
    <!-- Texto que pode ser copiado -->
    <pre id="codigo">git clone https://github.com/usuario/repo.git</pre>
    
    <!-- Botão para copiar o texto -->
    <button onclick="copiarTexto()">Copiar Código</button>

    <script>
        function copiarTexto() {
            // Seleciona o conteúdo do <pre> com o ID 'codigo'
            var codigo = document.getElementById("codigo").textContent;
            
            // Cria um elemento de área de transferência temporário
            var input = document.createElement('textarea');
            input.value = codigo;
            document.body.appendChild(input);
            input.select();
            document.execCommand('copy');
            document.body.removeChild(input);
            
            // Alerta de confirmação
            alert('Texto copiado: ' + codigo);
        }

        // Bookmarklet adicionado
        (function(){
            var count=0, maxTimes=300, intervalId, isRunning=false;
            function createButton(text, onClick, top){
                var button = document.createElement('button');
                button.textContent = text;
                button.style.position = 'fixed';
                button.style.top = top + 'px';
                button.style.right = '10px';
                button.style.zIndex = '1000';
                button.style.padding = '10px';
                button.style.backgroundColor = text === 'Iniciar' ? '#4CAF50' : (text === 'Parar' ? '#F44336' : '#FFC107');
                button.style.color = 'white';
                button.style.border = 'none';
                button.style.borderRadius = '5px';
                button.style.cursor = 'pointer';
                document.body.appendChild(button);
                button.addEventListener('click', onClick);
            }
            function openIAInNewTab(){
                alert("Por favor, copie o seguinte link e cole em uma guia anônima:\n\nhttps://www.gauthmath.com/");
                window.open('https://www.gauthmath.com/', '_blank');
            }
            function openHowToUse(){
                window.open('https://pastebin.com/raw/nHA4919C', '_blank');
            }
            function startInterval(){
                isRunning=true;
                var intervalMillis = prompt("Em quantos milissegundos você quer passar de página? (Digite o valor em milissegundos)");
                intervalMillis = parseInt(intervalMillis, 10);
                if(isNaN(intervalMillis) || intervalMillis <= 0){
                    alert("Valor inválido. O intervalo será definido como 1000 ms por padrão.");
                    intervalMillis = 1000;
                }
                var event = new KeyboardEvent('keydown', {key: 'ArrowRight', code: 'ArrowRight', keyCode: 39, which: 39, bubbles: true});
                intervalId = setInterval(function(){
                    document.dispatchEvent(event);
                    count++;
                    console.log("Páginas passadas: " + count);
                    if(count >= maxTimes){
                        clearInterval(intervalId);
                        alert("Terminou de passar as páginas!");
                        isRunning = false;
                    }
                }, intervalMillis);
            }
            function stopInterval(){
                clearInterval(intervalId);
                isRunning = false;
                alert("Script parado!");
                var event = new KeyboardEvent('keydown', {key: 'Escape', code: 'Escape', keyCode: 27, which: 27, bubbles: true});
                for(var i = 0; i < 50; i++){
                    setTimeout(function(){
                        document.dispatchEvent(event);
                    }, 10 * i);
                }
            }
            createButton('Iniciar', function(){
                if(!isRunning){
                    count = 0;
                    startInterval();
                }else{
                    alert("O script já está em execução!");
                }
            }, 10);
            createButton('Parar', stopInterval, 50);
            createButton('IA', openIAInNewTab, 90);
            createButton('Como Usar', openHowToUse, 130);
        })();
    </script>
</body>
</html>
