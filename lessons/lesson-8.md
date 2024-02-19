# Pula 8 (stash)

Quando estamos trabalhando em uma branch e precisamos mudar de branch, mas ainda não terminamos o que estamos fazendo podemos usar o comando `git stash` pra salvar o estado atual da branch e depois voltar pra ela e continuar o que estávamos fazendo.
Stash funciona como uma pilha, então podemos salvar o estado atual da branch e depois voltar pra ela e salvar o estado atual novamente e assim por diante.

**No fim desse arquivo teremos um exercício prático antes de seguir para a próxima aula.**

## Stash

Git stash é um conceito de armazenamento temporário de alterações que não foram commitadas ainda.
Funciona como uma pilha, então podemos salvar o estado atual da branch e depois voltar pra ela e salvar o estado atual novamente e assim por diante.

Para colocar alterações na pilha de stash usamos o comando `git stash` e pra voltar o estado da pilha de stash pra branch usamos o comando `git stash pop`.

Esse é um comando bem comum quando precisamos pausar nosso trabalho corrente por algum motivo pra revisar algo, ajudar alguém ou até mesmo ajustar alguma outra branch e posteriormente podemos retomar o que estávamos fazendo.

Para mais informações sobre stash: https://git-scm.com/docs/git-stash


# Prática 8

1. Use o comando `git stash list` para listar o que está na sua stash
2. Altere o título dessa aula pra `# Aula 8 (stash)`
3. Use o comando `git stash` e `git stash list` pra listar o que está na sua stash
4. Altere o fim desse arquivo de `lesson-8` pra `lesson-9`
5. Use o comando `git stash` e `git stash list` pra listar o que está na sua stash
6. Repare que o arquivo `lesson-8` não contem suas mudanças e vamos rodar `git stash pop` para desempilhar a ultima alteração
7. Agora vamos rodar `git stash list` pra ver o que temos na stash
8. Vamos rodar `git stash pop` pra desempilhar a ultima alteração
9. Agora com as 2 alterações no arquivo `lesson-8.md` podemos adicionar as alterações com `git add .` e depois `git commit -m "fix: lesson 9 reference"`

--- 

Podemos seguir para a próxima aula na branch `lesson-8`.