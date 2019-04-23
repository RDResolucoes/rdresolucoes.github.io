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
    			document.getElementById("cpf").innerHTML = "ERRO: dados inválids";    					return;
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
    <p id="nome" name="nome">NOME: </p>
    <p id="cpf" name="cpf">CPF: </p>
    <p id="num" name="num">NÚMERO DE MATERIAIS: </p>
    <p id="tempo" name="tempo">TEMPO DE TRABALHO: </p>
    <p>ASSUNTOS: </p>
    <p id="assuntos" name="assuntos"></p>
</body></html>
