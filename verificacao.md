---
title: Verificação de Certificado
permalink: verificacao.html
layout: default
description: Bem vindo! Verifique a validade dos dados do certificado!
---



<html><head>    
    <script type="text/javascript">
    	function httpGet(theUrl) {
            var xmlHttp = new XMLHttpRequest();
            xmlHttp.open( "GET", theUrl, false ); // false for synchronous request
            xmlHttp.send( null );
            return xmlHttp.responseText.split('class="softmerge-inner"')[1].split(">")[1].split("<")[0];
        };
    	
    	function search(){
    		var doc_url = "https://docs.google.com/spreadsheets/d/1uSAoq6YB6vYt7urYJPBcj3QfTQ57K-FnXzp0dBwj0OM/pubhtml";
    		var url = window.location.href;
    		var line = url.split("line=")[1].split("&")[0];
    		var cpf = url.split("cpf=")[1].split("&")[0];
    		var doc_cpf = httpGet(doc_url.concat("?gid=0&single=true&range=A",line));
    		if(cpf!=doc_cpf) {
    			document.getElementById("cpf").innerHTML = "<h1>ERRO: dados inválids</h1>";    
                document.getElementById("nome").innerHTML = "";    
                document.getElementById("num").innerHTML = "";    
                document.getElementById("tempo").innerHTML = "";    
                document.getElementById("assuntost").innerHTML = "";    							return;
    		}
    		var nome = httpGet(doc_url.concat("?gid=0&single=true&range=B",line));
    		var num = httpGet(doc_url.concat("?gid=0&single=true&range=D",line));
    		var tempo = httpGet(doc_url.concat("?gid=0&single=true&range=E",line));
    		document.getElementById("nome").innerHTML += nome;    
    		document.getElementById("cpf").innerHTML += cpf;    
    		document.getElementById("tempo").innerHTML += tempo;    
    		document.getElementById("assuntos").innerHTML += tempo;    
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
