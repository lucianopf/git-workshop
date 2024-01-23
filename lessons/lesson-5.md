# Aula 5 (cherry-pick)

Eventualmente precisamos reaproveitar commits de outras branches sem fazer merge ou rebase, só trazendo um commit específico de outra branch. Para isso, temos o comando `cherry-pick`.

Referencia mais avançada: https://git-scm.com/docs/git-cherry-pick

**No fim desse arquivo teremos um exercício prático antes de seguir para a próxima aula.**

## Cherry-pick
Esse comando nos permite recuperar um commit específico de outra branch e aplicar na branch atual.
É um comando eventualmente usado quando queremos só trazer algumas poucas mudanças de uma branch.

Por exemplo, quando temos 2 pessoas desenvolvedoras trabalhando em features semelhantes que dependem da mesma base e uma delas termina primeiro, podemos usar o `cherry-pick` para trazer só o commit que cria a base da outra pessoa para a branch atual.

```bash
git cherry-pick <hash do commit>
```

Como esse é um comando que manipula o histórico de commits das branches, é importante ter cuidado ao usá-lo. Pois ele pode gerar conflitos que precisam ser resolvidos manualmente assim como rebase e merge.

Doc exemplificando quando isso acontece: https://www.themoderncoder.com/fix-git-cherry-pick-merge-conflicts/

# Prática 5

**Ao fim desse arquivo** temos a instrução errada pra seguir pra `lesson-5`, onde o correto deveria ser `lesson-6`. Vamos buscar a correção disso na branch `lesson-5.1` e trazer para a branch atual usando `cherry-pick`.

1. Vamos primeiro usar o `git log --one-line` pra ver o histórico de commits e vamos perceber que só temos 1 commit nessa branch atual
2. Iremos pra branch lesson-5.1 usando o comando `git checkout lesson-5.1`
3. Vamos usar o `git log --one-line` pra ver o histórico de commits e vamos perceber que temos 2 commits a frente da branch `lesson-5` e queremos recuperar o commit `fix: lesson 5 reference` que é o primeiro commit dessa branch.
4. Vamos copiar o hash do commit `fix: lesson 5 reference` e voltar pra branch `lesson-5` usando o comando `git checkout lesson-5`
5. Agora vamos usar o comando `git cherry-pick <hash do commit>` pra trazer o commit `fix: lesson 5 reference` pra branch `lesson-5`	
6. Vamos usar o `git log --one-line` pra ver o histórico de commits e vamos perceber que temos 2 commits e o estado correto da branch `lesson-5` com o `lesson-5.md` apontando pra branch `lesson-6`

--- 

Podemos seguir para a próxima aula na branch `lesson-6`.