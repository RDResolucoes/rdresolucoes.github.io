---
title: Produção de Conteúdo
permalink: producao.html
layout: default
description: Olá, coordenador! Nesta página está explicado passo a passo como proceder em diversas situações possíveis ao longo da sua jornada como membro da RDResoluções!
---


[*Forms de Preenchimento de Dados Bancários*](https://goo.gl/forms/1htaFiIdI0lXK9Fk2)

[*Forms de Cadastro de Membros*](https://goo.gl/forms/6qz8SDPxvC4NT2Sb2)

[*Lista de Assuntos LT-MEQRD Atuais*](https://docs.google.com/spreadsheets/d/e/2PACX-1vRhYIqMqNkNiFRYDf90of6DkRSftb-lDpu_fkQTfnlPGrMPjjkF-RQTGfkJBG6BfMvLSTznw6CSYB0w/pubhtml?gid=0&single=true)

[*Lista de Assuntos LT-PDRD Atuais*](https://docs.google.com/spreadsheets/d/e/2PACX-1vSGQ8uUcUeEme7Dyyf-yBvDFq1GdV6-gFXyHk8l4JuqWb9CRpw1kh45rk3UQ4ktdXWyfyQwxX6uWtcj/pubhtml?gid=1755051344&single=true)

## Templates de Listas Teóricas Produzidas

[LT-MEQRD](https://drive.google.com/uc?export=download&id=1BYUKw9zofkAXIA39-Hy2Ryn3QQWa-MkH)

[LT-PDRD](https://drive.google.com/uc?export=download&id=1_8tl0pgdzQpbouXN5hIYg-ah025PIGQf)

## Gerador de AID´s

<html><head>    
    <script type="text/javascript">
      function aidSubmit() {
        var str = document.formulario.cpf.value;
        str = str.replace(/\D/g,'');
        if(!validarCPF(str))
            document.getElementById("aid").value = "ERRO";
        else {
            document.getElementById("aid").value = "1";
            for (var i = 8; i >= 0; i-=2)
              document.getElementById("aid").value += str.charAt(i);
            for (var i = 7; i > 0; i-=2)
              document.getElementById("aid").value += str.charAt(i);
        }
      };

        function validarCPF(cpf) {    
            cpf = cpf.replace(/[^\d]+/g,'');    
            if(cpf == '') return false;    
            // Elimina CPFs invalidos conhecidos    
            if (cpf.length != 11 ||
            cpf == "00000000000" ||
            cpf == "11111111111" ||
            cpf == "22222222222" ||
            cpf == "33333333333" ||
            cpf == "44444444444" ||
            cpf == "55555555555" ||
            cpf == "66666666666" ||
            cpf == "77777777777" ||
            cpf == "88888888888" ||
            cpf == "99999999999")
                return false;        
            // Valida 1o digito    
            add = 0;    
            for (i=0; i < 9; i ++)        
                add += parseInt(cpf.charAt(i)) * (10 - i);    
                rev = 11 - (add % 11);    
                if (rev == 10 || rev == 11)        
                    rev = 0;    
                if (rev != parseInt(cpf.charAt(9)))        
                    return false;        
            // Valida 2o digito    
            add = 0;    
            for (i = 0; i < 10; i ++)        
                add += parseInt(cpf.charAt(i)) * (11 - i);    
            rev = 11 - (add % 11);    
            if (rev == 10 || rev == 11)    
                rev = 0;    
            return (rev == parseInt(cpf.charAt(10)))
        };
    </script>
  </head>
  <body>
    <form id="formulario" name="formulario">
      CPF:<br>
      <input type="text" name="cpf" id="cpf"><br>
      AID:<br>
      <input type="text" name="aid" id="aid">
      <input type="button" value="Gerar" onclick="aidSubmit();"><br><br>
    </form>
</body></html>
