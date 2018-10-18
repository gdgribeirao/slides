# Git Hooks: o que são e como usá-los

Os hooks não são exclusividade do GIT. Em verdade, praticamente todo sistema de
controle de versões de código moderno tem uma forma de hook. A ideia por trás do
hook é permitir que o controlador de versões integre-se de forma mais natural ao
seu fluxo de trabalho. Por exemplo, imagine que você tenha uma forma padronizada
de comentários. Você pode forçar o usuário a seguir esta forma padronizada
instalando um hook de pre-commit no repositório. Este hook pode analisar o
comentário e verificar se o mesmo segue um determinado formato.

Os hooks são usados normalmente em empresas que implementam um ciclo completo de
desenvolvimento, com rastreamento de requisitos do documento ao código. Este
tipo de rastreamento envolve a integração das modificações no código com algum
sistema de controle de requisitos ou problemas (issue tracker).

Assim, o hook é usado para lançar no sistema de controle de versões quais as
alteraçòes que foram feitas em qual arquivo para qual issue. 

## Onde estão os hooks

Os hooks normalmente estão dentro do diretório .git/hooks, se você tem uma
working tree clonada de um repositório. Nos repositórios _bare_ os hooks estão
no diretório hooks. Ao criar um repositório, este diretório vem com uma série de
arquivos de exemplo que demonstram como escrever seu hook.

Uma coisa muito importante para se ter em mente: todos os scripts foram
projetados para execução em algum shell linux ou unix. Porém você pode escrever
seus hooks em python ou ruby ou na linguagem de scripting da sua preferência.

## Cenários comuns de uso

Existem alguns cenários interessantes que podem usar o git hook como uma
ferramenta de integração e, até mesmo, validação. Por exemplo, digamos que o seu
projeto tem um padrão bem estabelecido de comentários. Um hook de pré-commit
pode validar o conteúdo dos comentários antes de realizar o commit, impedindo a
operação se o comentário estiver fora de padrão.

Um outro uso refere-se à rastreabilidade: você pode integrar um commit com uma
ferramenta de bug tracking, armazenando na ferramenta de bug tracking quais
arquivos foram alterados para aquele commit.

Há ainda um outro cenário no qual você pode forçar a indentação do código para
determinado formato, chamando um code styler em um hook de pré-commit para
garantir que o código sempre será carregado no repositório de acordo com os
padrões da empresa.

Além de validações, é possível usar os hooks para integrações com sistemas de
compilação e automações dos mais diversos tipos e necessidades.

# Mais Informações

Vale a pena dar uma lida [neste
artigo](http://git-scm.com/book/pt-br/Customizando-o-Git-Hooks-do-Git). Os
principais hooks estão cobertos e há explicação de qual parâmetro cada um deles
utiliza-se para validar os commits e outras operaçòes do GIT.
