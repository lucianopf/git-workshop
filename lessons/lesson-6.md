# Aula 6 (revert)

Eventualmente fazemos mudanças indesejadas, o que é comum. Nesses casos, gostaríamos de realizar um rollback/revert do que foi feito, para voltar ao estado anterior.
Podemos reescrever tudo como era antes, mas isso pode ser trabalhoso, demorado, ineficiente e muitas vezes ocorrer um outro erro durante esse processo. Então, temos o comando `revert`, que nos permite fazer um rollback de um commit específico.

**No fim desse arquivo teremos um exercício prático antes de seguir para a próxima aula.**

## Revert

Esse comando nos permite fazer um rollback de um commit específico, criando um novo commit que desfaz as mudanças do commit especificado.
É um comando bem importante especialmente em casos de incidentes e bugs que precisam ser corrigidos rapidamente.

```bash
git revert <hash do commit>
```

Obs: nesse caso estamos falando sobre o `git revert` e não o botão Revert do github, que faz um squash de commits e o revert desse commit pra poder fazer o revert de multiplos commits de uma vez.

Referencia mais avançada: https://git-scm.com/docs/git-revert

# Prática 6

No final dessa aula temos a instrução errada pra seguir pra `lesson-6`, mas na verdade deveríamos utilizar `lesson-7`. Vamos reverter a mudança que introduziu esse problema.

1. Vamos primeiro usar o `git log --one-line` pra ver o histórico de commits e vamos perceber que temos 2 commits nessa branch atual
2. Vamos copiar o hash do commit `chore: lesson 6 reference` e usar o comando `git revert <hash do commit>` pra reverter o commit `chore: lesson 6 reference`
3. Vamos usar o `git log --one-line` pra ver o histórico de commits e vamos perceber que temos 3 commits e o estado correto da branch `lesson-6` com o `lesson-6.md` apontando pra branch `lesson-7`

--- 

Podemos seguir para a próxima aula na branch `lesson-7`.