---
title: Verificação de Certificado
permalink: verificacao.html
layout: default
description: Bem vindo! Verifique a validade dos dados do certificado!
---



<html><head>    
    <script type="text/javascript">
    	function setCPF(){
    		var url = window.location.href;
    		var line = url.split("line=")[1].split("&")[0];
    		var cpf = url.split("cpf=")[1].split("&")[0];
    		document.getElementById("cpf").value = cpf;
    		document.getElementById("line").value = line;
    	};
    	
    	function httpGet(theUrl) {
            var xmlHttp = new XMLHttpRequest();
            xmlHttp.open( "GET", theUrl, false ); // false for synchronous request
            xmlHttp.send( null );
            return xmlHttp.responseText;
        };
    	
    	function search(){
    		var doc_url = "https://docs.google.com/spreadsheets/d/1uSAoq6YB6vYt7urYJPBcj3QfTQ57K-FnXzp0dBwj0OM/pubhtml";
    		var url = window.location.href;
    		var line = url.split("line=")[1].split("&")[0];
    		var cpf = url.split("cpf=")[1].split("&")[0];
    		var doc_cpf = httpGet(doc_url.concat("?gid=0&single=true&range=A",line));
    		document.getElementById("cpf1").text = cpf;
    		document.getElementById("cpf2").text = doc_cpf;
    	};
    </script>
  </head>
  <body onload="setCPF();">
        <form action="#" onsubmit="search();" method="get">
      CPF: <input id="cpf" type="text" value="" readonly><input type="submit" value="Buscar"><br>
          <input id="line" name="line" type="hidden" value=""><br>
    </form>
    <p id="nome" name="nome">value</p>
    <p id="cpf1" name="cpf1"></p>
    <p id="cpf2" name="cpf2"></p>
</body></html>
