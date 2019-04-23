---
title: Verificação de Certificado
permalink: verificacao.html
layout: default
description: Bem vindo! Verifique a validade dos dados do certificado!
---



<html><head>    
    <script type="text/javascript">
    	function httpGet(range) {
    		var theUrl = "https://docs.google.com/spreadsheets/d/1uSAoq6YB6vYt7urYJPBcj3QfTQ57K-FnXzp0dBwj0OM/pubhtml?gid=0&single=true&range=".concat(range);
            var xmlHttp = new XMLHttpRequest();
            xmlHttp.open( "GET", theUrl, false ); // false for synchronous request
            xmlHttp.send( null );
            return xmlHttp.responseText;
        };
        
        function getCPF(line) {
                return httpGet("A".concat(line)).split('class="softmerge-inner"')[1].split(">")[1].split("<")[0];
        };
        
        function getName(line) {
                return httpGet("B".concat(line)).split('class="s0"')[1].split(">")[1].split("<")[0];
        };
        
        function getNum(line) {
                return httpGet("D".concat(line)).split('class="s0"')[1].split(">")[1].split("<")[0];
        };
        
        function getTime(line) {
                return httpGet("E".concat(line)).split('class="s0"')[1].split(">")[1].split("<")[0];
        };
        
        function getSubj(line) {
                return httpGet("C".concat(line)).split('class="softmerge-inner"')[1].split(">")[1].split("<")[0];
        };
    	
    	function search(){
    		var url = window.location.href;
    		var line = url.split("line=")[1].split("&")[0];
    		var cpf = url.split("cpf=")[1].split("&")[0];
    		var doc_cpf = getCPF(line);
    		if(cpf!=doc_cpf) {
    			document.getElementById("cpf").innerHTML = "<h1>ERRO: dados inválids</h1>";    
                document.getElementById("nome").innerHTML = "";    
                document.getElementById("num").innerHTML = "";    
                document.getElementById("tempo").innerHTML = "";    
                document.getElementById("assuntost").innerHTML = "";    							return;
    		}
    		var nome = getName(line);
    		var num = getNum(line);
    		var tempo = getTime(line);
    		var assuntos = getSubj(line).split(";");
    		document.getElementById("nome").innerHTML += nome;    
    		document.getElementById("cpf").innerHTML += cpf;    
    		document.getElementById("num").innerHTML += num;    
    		document.getElementById("tempo").innerHTML += tempo;    
    		document.getElementById("assuntos").innerHTML += "<ul>";    
    		//for(var i=0; i<assuntos.length; i++)
    			//document.getElementById("assuntos").innerHTML += "<li>".concat(assuntos[i],";</li>"); 
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
