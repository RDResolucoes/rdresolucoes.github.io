---
title: Verificação de Certificado
permalink: verificacao.html
layout: default
description: Bem vindo! Verifique a validade dos dados do certificado!
---



<html><head>    
    <script type="text/javascript">
    	function httpGet(range) {
    		if(!isNaN(range))
    			range = range.concat("%3A",range);
    		var theUrl = "https://docs.google.com/spreadsheets/d/1uSAoq6YB6vYt7urYJPBcj3QfTQ57K-FnXzp0dBwj0OM/pubhtml?gid=0&single=true&range=".concat(range);
            var xmlHttp = new XMLHttpRequest();
            xmlHttp.open( "GET", theUrl, false ); // false for synchronous request
            xmlHttp.send( null );
    		console.log(theUrl);
    		console.log(xmlHttp.responseText);
            return xmlHttp.responseText;
        };
        
        function getLine(line) {
                return httpGet(line);
        };
        
        function getCPF(line) {
                return line.split('class="softmerge-inner"')[1].split(">")[1].split("<")[0];
        };
        
        function getName(line) {
                return line.split('class="s0"')[1].split('>')[1].split('<')[0];
        };
        
        function getNum(line) {
                return line.split('class="s2"')[1].split('>')[1].split('<')[0];
        };
        
        function getTime(line) {
                return line.split('class="s2"')[2].split('>')[1].split('<')[0];
        };
        
        function getSubj(line) {
                return line.split('class="softmerge-inner"')[2].split(">")[1].split("<")[0].split(';');
        };
    	
    	function search(){
    		var url = window.location.href;
    		var line = url.split("line=")[1].split("&")[0];
    		var cpf = url.split("cpf=")[1].split("&")[0];
    		var tudo = getLine(line);
    		var doc_cpf = getCPF(tudo);
    		if(cpf!=doc_cpf) {
    			document.getElementById("cpf").innerHTML = "<h1>ERRO: dados inválids</h1>";    
                document.getElementById("nome").innerHTML = "";    
                document.getElementById("num").innerHTML = "";    
                document.getElementById("tempo").innerHTML = "";    
                document.getElementById("assuntost").innerHTML = "";    							return;
    		}
    		var nome = getName(tudo);
    		var num = getNum(tudo);
    		var tempo = getTime(tudo);
    		var assuntos = getSubj(tudo);
    		document.getElementById("nome").innerHTML += nome;    
    		document.getElementById("cpf").innerHTML += cpf;    
    		document.getElementById("num").innerHTML += num;    
    		document.getElementById("tempo").innerHTML += tempo.concat(" horas");    
    		document.getElementById("assuntos").innerHTML += "<ul>";   
    		for(var i=0; i<assuntos.length; i++)
    			document.getElementById("assuntos").innerHTML += "<li>".concat(assuntos[i],";</li>"); 
    		document.getElementById("assuntos").innerHTML += "</ul>"; 
    	};
    </script>
  </head>
  <body onload="search();">
    <p id="nome" name="nome"><strong>NOME</strong>: </p>
    <p id="cpf" name="cpf"><strong>CPF</strong>: </p>
    <p id="num" name="num"><strong>NÚMERO DE MATERIAIS</strong>: </p>
    <p id="tempo" name="tempo"><strong>TEMPO DE TRABALHO</strong>: </p>
    <p id="assuntost" name="assuntost"><strong>ASSUNTOS</strong>: </p>
    <p id="assuntos" name="assuntos"></p>
</body></html>
