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
    		document.getElementById("range").value = line.concat(":",line);
    	};
    </script>
  </head>
  <body onload="setCPF();">
        <form action="https://docs.google.com/spreadsheets/d/1uSAoq6YB6vYt7urYJPBcj3QfTQ57K-FnXzp0dBwj0OM/pubhtml" method="get" target="_blank">
      CPF: <input id="cpf" type="text" value="" readonly><br>
          <input name="gid" type="text" value="0"><br>
          <input name="single" type="text" value="true"><br>
          <input id="range" name="range" type="text" value=""><br>
      <input type="submit" value="Buscar"><br><br>
    </form>
</body></html>
