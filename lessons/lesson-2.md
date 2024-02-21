# Aula 2 (status, log)

Agora que estamos em uma versão do repositório, local é interessante começar a conseguir visualizar o que temos de informação básica pra consulta.

## Status

De forma geral, esse comando da um resumo do estado atual do repositório, ele mostra se temos arquivos modificados, se temos arquivos novos, se temos arquivos deletados, se temos arquivos prontos para realizar commit, se temos arquivos prontos para serem enviados para o repositório remoto, etc...

Para executar o comando, basta executar `git status`. Como não temos nada modificado no momento, não é esperado ter muita informação como resultado desse comando. Mas, logo logo iremos utiliza-lo bastante pra ajudar a compreender o estado do repositório.


## Log

Esse comando é um dos mais importantes do git, ele mostra o histórico de commits do repositório, ele mostra quem fez o commit, quando foi feito, qual foi a mensagem do commit e qual foi o hash do commit.

Para executar o comando basta executar `git log`.

Temos diversas variações desse comando que podemos consultar usando o help `git log --help`.

Atualmente o comando de visualizar logs que mais uso é o `git log --one-line` que traz de forma mais resumida o histórico de commits.
Temos também o comando `git log --graph` que renderiza no terminal uma representação gráfica do histórico de commits e branches. 

Obs: é possível configurar o padrão do log usando `git config --global format.pretty oneline` e daí em diante qualquer `git log` será  `--one-line`

--- 

Podemos seguir para a próxima aula na branch `lesson-3`.