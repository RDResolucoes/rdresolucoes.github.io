---
title: Questionário Base - Códigos de Resposta
permalink: codigosqb.html
layout: default
---

# Códigos de Resposta
Copie o código desejado abaixo antes de começar a responder o questionário
## *Texto Comum*
```
---
==Resposta(Texto)==
{
conteúdo
}

---
```
## *Um Pouco de História*
```
---
==Resposta(Título)==
{
conteúdo
}

---
==Resposta(Texto)==
{
conteúdo
}

---
==Resposta(Fonte)==
{
conteúdo
}
---
```
## *Referências*
```
---
==Resposta(Referências)==
{
conteúdo
}

---
```
## *Flashcard Interativo*
```
---
==Resposta(Template){cartao_n}{numero_da_template}==
{
==Resposta(Flashcard Interativo)==
{
conteúdo
}
}

---
```
## *Flashcard Interativo com Zoom*
```
---
==Resposta(Flashcard Interativo){cartao_n}{10}==
{
==Resposta(Flashcard Interativo)==
{
|==Elemento==|==Flashcard==|==Fala(Áudio Transcrito)==|==Áudio==|
|:--:|:----:|:----:|:--:|
|**Título**|**Elemento**|**Fala**|**áudio**|
|**Imagem A**|**IMAGEM MÃE**[]![]()[][]|**Fala**|**áudio**|
|**ZOOM 1**|[ZOOM 1]![]()[][]|**Fala**|**áudio**|
|**ZOOM 2**|[ZOOM 2]![]()[][]|**Fala**|**áudio**|
|**ZOOM 3**|[ZOOM 3]![]()[][]|**Fala**|**áudio**|
|**ZOOM n**|[ZOOM n]![]()[][]|**Fala**|**áudio**|
|**ZOOM n2**|[ZOOM n2]![]()[][]|**Fala**|**áudio**|
}
}

---
```
## *Bullet*
```
---
==Resposta(Bullet)==
{
conteúdo
}

---
```
## *Diagramas*
```
---
==Resposta(Diagrama)==
{
```mermaid
graph TD
A[lala]-->|de la para sol|B[solsol]
B-.->C
```apagaressafrase
}

---
```

## *Explicação detalhada sem Exemplo*
```
---
==Resposta(Explicação Detalhada){topico_n}==
{
conteúdo
}

---
```
## *Explicação detalhada com Exemplo*
```
---
==Resposta(Explicação Detalhada){topico_n}==
{
conteúdo

==Resposta(Exemplo)==
{
conteúdo
}
}

---
```
## *Exercício sem alternativa*
```
---
==Resposta(Exercício){Nome_do_Autor_da_Fonte}==
{
conteúdo
}

---
```
## *Resolução sem alternativa*
```
---
==Resposta(Resolução)==
{
conteúdo
}

---
```
## *Exercício com alternativa*
numeração corresponde às alternativas
```
---
==Resposta(Exercício){Nome_do_Autor_da_Fonte}==
{
Enunciado

1.
2.
3.
4.

}

---
```
## *Resolução com alternativa*
```
---
==Resposta(Resolução)==
{

1.
2.
3.
4.
}

---
```
## *Livre*
```
---
==Resposta(Livre){Tipo_de_Resposta}==
{
conteúdo
}

---
```

[back](./)