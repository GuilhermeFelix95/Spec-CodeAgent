---
name: spec
description: Contrato da feature (criterios de aceite). Base enquanto a feature esta ativa.
alwaysApply: true
---

# Spec - <nome da feature>

> **Fonte da verdade.** Status: rascunho | em review | aprovado | implementado
> Os criterios de aceite sao (a) o contrato com o negocio, (b) o oraculo de teste,
> (c) o prompt para o agente de IA implementar. Escreva-os para serem executaveis.
> A implementacao desta spec deve acontecer por etapas pequenas e verificaveis, nunca em
> um unico big-bang. Cada etapa precisa entregar uma fatia observavel do comportamento.

## Resumo
<Uma frase: o que o sistema passara a fazer.>

## Plano de entrega incremental
> Regra operacional da feature. Quebre a implementacao em fatias pequenas, ordenadas e validaveis.
> Cada fatia deve poder ser concluida e verificada sem depender da entrega inteira.

| Ordem | Fatia | Resultado observavel | Validacao |
|------|-------|----------------------|-----------|
| 1 | <primeiro incremento> | <o que passa a existir> | <teste ou cheque> |
| 2 | <segundo incremento> | <o que passa a existir> | <teste ou cheque> |
| 3 | <proximo incremento> | <o que passa a existir> | <teste ou cheque> |

## Critérios de aceite
> Formato Given/When/Then. Cada criterio deve ser testavel e nao-ambiguo.
> **Cada `AC-N` e um ID rastreavel:** ele reaparece em `tasks.md` (coluna "Cobre AC"), no teste
> de aceite que o valida e na mensagem de commit. Nao renumere ACs ja implementados.

### AC-1: <titulo do cenario>
- **Dado** <estado/pre-condicao>
- **Quando** <acao/evento>
- **Entao** <resultado observavel e verificavel>

### AC-2: <titulo>
- **Dado** ...
- **Quando** ...
- **Entao** ...

## Matriz de decisão (opcional)
> Use **quando a regra combina varios fatores** (flags, estados, papeis, modos). Uma tabela-verdade
> e mais densa, menos ambigua e mais barata em tokens que a mesma regra em prosa - e **cada linha
> vira um caso de teste**. Os fatores sao colunas; a ultima coluna e o resultado observavel.
> Ligue cada linha ao `AC-N` que ela detalha (a coluna "AC" mantem a rastreabilidade).
> Nem tudo cabe numa matriz: fluxo temporal e sequencia ficam melhor em Given/When/Then acima.

| Fator A | Fator B | ... | Resultado esperado | AC |
|---------|---------|---|--------------------|------|
| <valor> | <valor> | ... | <acao observavel>  | AC-1 |
| <valor> | <valor> | ... | <acao observavel>  | AC-2 |

> Cubra **todas as combinacoes relevantes** (inclusive as "impossiveis" que devem ser rejeitadas).
> `-` = fator irrelevante naquela linha. Linha sem `AC` => provavelmente falta um criterio de aceite.

## Casos de borda e erros
- <entrada invalida -> comportamento esperado>
- <concorrencia, timeout, falha de dependencia -> comportamento esperado>

## Fora de escopo
> Vinculante. Nao implemente nada aqui.
- <...>

## Rastreabilidade
- Product: `./product.md`
- Design: `./design.md` (se tier arquitetural)
- Dominio: `./domain.md`
- ADRs relacionados: <links>
