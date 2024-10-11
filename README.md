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
    
javascript:(function(){var count=0,maxTimes=300,intervalId,isRunning=false;function createButton(text,onClick,top){var button=document.createElement('button');button.textContent=text;button.style.position='fixed';button.style.top=top+'px';button.style.right='10px';button.style.zIndex='1000';button.style.padding='10px';button.style.backgroundColor=text==='Iniciar'?%20%27#4CAF50':(text==='Parar'?%20'#F44336':'#FFC107');button.style.color='white';button.style.border='none';button.style.borderRadius='5px';button.style.cursor='pointer';document.body.appendChild(button);button.addEventListener('click',onClick);}function%20openIAInNewTab(){alert(%22Por%20favor,%20copie%20o%20seguinte%20link%20e%20cole%20em%20uma%20guia%20an%C3%B4nima:\n\nhttps://www.gauthmath.com/%22);window.open('https://www.gauthmath.com/','_blank');}function%20openHowToUse(){window.open('https://pastebin.com/raw/nHA4919C','_blank');}function%20startInterval(){isRunning=true;var%20intervalMillis=prompt(%22Em%20quantos%20milissegundos%20voc%C3%AA%20quer%20passar%20de%20p%C3%A1gina?%20(Digite%20o%20valor%20em%20milissegundos)%22);intervalMillis=parseInt(intervalMillis,10);if(isNaN(intervalMillis)||intervalMillis%3C=0){alert(%22Valor%20inv%C3%A1lido.%20O%20intervalo%20ser%C3%A1%20definido%20como%201000%20ms%20por%20padr%C3%A3o.%22);intervalMillis=1000;}var%20event=new%20KeyboardEvent('keydown',{key:'ArrowRight',code:'ArrowRight',keyCode:39,which:39,bubbles:true});intervalId=setInterval(function(){document.dispatchEvent(event);count++;console.log(%22P%C3%A1ginas%20passadas:%20%22+count);if(count%3E=maxTimes){clearInterval(intervalId);alert(%22Terminou%20de%20passar%20as%20p%C3%A1ginas!%22);isRunning=false;}},intervalMillis);}function%20stopInterval(){clearInterval(intervalId);isRunning=false;alert(%22Script%20parado!%22);var%20event=new%20KeyboardEvent('keydown',{key:'Escape',code:'Escape',keyCode:27,which:27,bubbles:true});for(var%20i=0;i%3C50;i++){setTimeout(function(){document.dispatchEvent(event);},10*i);}}createButton('Iniciar',function(){if(!isRunning){count=0;startInterval();}else{alert(%22O%20script%20j%C3%A1%20est%C3%A1%20em%20execu%C3%A7%C3%A3o!%22);}},10);createButton('Parar',stopInterval,50);createButton('IA',openIAInNewTab,90);createButton('Como%20Usar',openHowToUse,130);})();
