# Leia-me-sp-cheat

<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Botão de Copiar no GitHub Pages</title>
</head>
<body>
    <h1>Meu Projeto no GitHub</h1>
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
            
            // Alerta de 
