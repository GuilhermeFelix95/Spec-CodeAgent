---
name: tasks
description: Decomposicao e gates da feature. Puxe ao implementar.
alwaysApply: false
---

# Tasks - <nome da feature>

> Decomposicao da implementacao. Cada task **mapeia para um ou mais `AC-N`** (rastreabilidade
> spec -> task -> commit) e tem um **gate executavel**: o comando que prova que ela esta pronta.
> Marque `[P]` nas tasks que podem rodar em paralelo (sem dependencia entre si).
> Por padrao, prefira fatias pequenas e entregaveis: cada task deve fechar um incremento valido,
> nunca uma construcao inteira de uma vez.

## Plano
| #  | Task                                  | Cobre AC | Depende de | Gate (comando)        | Status |
|----|---------------------------------------|----------|------------|-----------------------|--------|
| 1  | <ex.: modelar agregado no dominio>    | AC-1     | -          | `<test do dominio>`    | todo   |
| 2  | <ex.: caso de uso na application>     | AC-1,2   | 1          | `<test do caso de uso>`| todo   |
| 3  | <ex.: adapter/repo na infrastructure> | AC-2     | 1          | `<test de integracao>` | todo   |
| 4  | <ex.: endpoint na interface> `[P]`    | AC-1,2   | 2,3        | `<test de aceite>`     | todo   |

> Uma task so vira `done` quando o **gate passa** (comandos em `docs/engineering/TESTING.md`) - nao por
> inspecao visual. Um commit por task.

## Plano de teste
- Unidade: <invariantes do dominio, value objects>
- Integracao: <adapters, repos, contratos>
- Aceite: <um teste por AC da spec.md - e o gate de aceite>

## Divergencias (SPEC_DEVIATION)
> Se a implementacao precisar fugir da spec, registre aqui antes de seguir (ver `AGENTS.md`).
- [ ] <task # · motivo · resolucao: corrigir codigo OU atualizar spec/ADR>

## Checklist de Definition of Done
- [ ] Todos os AC verdes **pelo gate executavel** (nao por inspecao)
- [ ] Nenhum `SPEC_DEVIATION` pendente
- [ ] ADRs de decisoes dificeis de reverter registrados
- [ ] Glossario / context-map atualizados se mudaram
- [ ] Spec reflete o que foi construido
- [ ] `docs/STATE.md` atualizado (proximo passo / decisoes)
