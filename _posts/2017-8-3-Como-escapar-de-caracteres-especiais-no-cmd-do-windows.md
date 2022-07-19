---
layout: post
title: Escapar de caracteres especiais no cmd do windows
tags: windows cmd
---

Todas as versões do DOS interpretam certos caracteres antes de executar um comando. Alguns exemplos bem conhecidos são o sinal de porcentagem `%` e os símbolos de redirecionamento `<` `|` `>`. Também permitem o uso de *carets* `^` para escapar de caracteres especiais.

Por exemplo, ao passarmos uma senha com virgula para o parâmetro `password`, precisamos colocar antes de `,` o `^`:

```bash
/password:"i@M}r43/3g%s^,L;"
                           ↑
```

Dessa forma a senha recebida será realmente a `i@M}r43/3g%s,L;`.


### **Tabela de Escape de Caracteres** 


| Caráter a ser<br>escapado	| Sequência<br>de fuga	 | Observação |
| :---: | :---: | :---: |
| % | %% | Não é sempre necessário em cordas duplas, apenas tente |
| ^ | ^^ |	Não pode sempre ser exigido em cordas duplas, mas não vai doer |
| & | ^& | |
| < | ^< | |
| > | ^> | |
| \| | ^\| | |
| ' | ^' |	Requerido apenas no "assunto" FOR / F (ou seja, entre os parênteses), a menos que backq seja usado |
| \` | ^\` |	Requerido apenas no "assunto" FOR / F (ou seja, entre os parênteses), se backq for usado |
| , | ^, |	Requerido apenas no "assunto" FOR / F (ou seja, entre os parênteses), mesmo em cordas duplas |
| ; | ^; | |
| = | ^= | |
| ( | ^( | |
| ) | ^) | |
| ! | ^^! |	Requerido apenas quando a expansão da variável atrasada está ativa |
| " | "" |	Requerido apenas dentro do padrão de pesquisa de ENCONTRAR |
| \ | \\\ |	Requerido apenas dentro do padrão regex da FINDSTR |
| [ | \\[ | |
| ] | \\] | |
| " | \\" | |
| . | \\. | |
| * | \\* | |
| ? | \\? | |


<sup>Fonte: http://www.robvanderwoude.com/escapechars.php</sup>
