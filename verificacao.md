---
title: Verificação de Certificado
permalink: verificacao.html
layout: default
description: Bem vindo! Verifique a validade dos dados do certificado!
---



<html><head>    
    <script type="text/javascript">
    	function setCPF(){
    		var line = window.location.searchParams.get("line");
    		document.getElementById("cpf").value = window.location.searchParams.get("cpf");
    		document.getElementById("range").value = line+":"+line;
    	}
    </script>
  </head>
  <body onload="setCPF();">
    <form action="https://docs.google.com/spreadsheets/d/1uSAoq6YB6vYt7urYJPBcj3QfTQ57K-FnXzp0dBwj0OM/pubhtml" method="get" target="_blank">
      CPF: <input id="cpf" type="text" readonly>
          <input id="line" type="hidden" value="">
          <input id="gid" type="hidden" value="0">
          <input id="single" type="hidden" value="true">
          <input id="range" type="hidden" value="">
      <input type="button" value="Buscar" onclick="submit();"><br><br>
    </form>
</body></html>
