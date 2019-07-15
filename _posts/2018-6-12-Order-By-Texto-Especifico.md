---
layout: post
title: Como ordenar uma consulta por texto especifico
---

A algum tempo foi preciso fazer a ordernação de uma coluna de uma maneira bem expecifica:
 - Aparecer por primeiro 3 registros expecificos.  
 
Isso sem nenhuma logica de ordenação possivel, veja abaixo como foi resolvido:

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

Resolvi fazendo um `CASE`, pois dessa forma se a "palavra" aparecesse seria ordenado pelo número 
correspondede a ela, 0,1 ou 2, caso contrario seria mostrado posterior as mesmas.
