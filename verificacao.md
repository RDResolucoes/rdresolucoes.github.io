---
title: Verificação de Certificado
permalink: verificacao.html
layout: default
description: Bem vindo! Verifique a validade dos dados do certificado!
---



<html><head>    
    <script type="text/javascript">
    	function setCPF(){
    		var line = window.location.href.searchParams.get("line");
    		var cpf = window.location.href.searchParams.get("cpf");
    		document.getElementById("cpf").value = "09275985669";
    		document.getElementById("range").value = line+":"+line;
    	}
    </script>
  </head>
  <body onload="setCPF();">
        <form action="https://docs.google.com/spreadsheets/d/1uSAoq6YB6vYt7urYJPBcj3QfTQ57K-FnXzp0dBwj0OM/pubhtml" method="get" target="_blank">
      CPF: <input id="cpf" type="text" value="" readonly><br>
          <input id="gid" type="text" value="0"><br>
          <input id="single" type="text" value="true"><br>
          <input id="range" type="text" value=""><br>
      <input type="button" value="Buscar" onclick="submit();"><br><br>
      <input type="button" value="Preencher" onclick="setCPF();"><br><br>
    </form>
</body></html>
