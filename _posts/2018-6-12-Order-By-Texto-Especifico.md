---
layout: post
title: Ordenar uma consulta por texto especifico com sql
tags: sql 
---

A algum tempo foi preciso fazer a ordenação de uma coluna de uma maneira bem especifica:
 - Aparecer por primeiro 3 registros especificos.  
 
Isso sem nenhuma lógica de ordenação possível, veja abaixo como foi resolvido:

```
SELECT
  descricao
FROM
  tabela
ORDER BY
CASE descricao
    WHEN 'textoUM'   THEN 0
    WHEN 'textoUM'   THEN 1
    WHEN 'textoDOIS' THEN 2
    ELSE 999
END
```

Resolvi fazendo um `CASE`, pois dessa forma se a "palavra" aparecesse seria ordenado pelo número correspondende a ela, 0,1 ou 2, caso contrário seria mostrado posterior as mesmas.
