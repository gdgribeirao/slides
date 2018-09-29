# Git Hooks: o que são e por que você provavelmente não usará

Os hooks não são exclusividade do GIT. Em verdade, praticamente todo sistema de
controle de versões de código moderno tem uma forma de hook. A ideia por trás do
hook é permitir que o controlador de versões integre-se de forma mais natural ao
seu fluxo de trabalho. Por exemplo, imagine que você tenha uma forma padronizada
de comentários. Você pode forçar o usuário a seguir esta forma padronizada
instalando um hook de pre-commit no repositório. Este hook pode analisar o
comentário e verificar se o mesmo segue um determinado formato.

Os hooks são usados normalmente em empresas que implementam um ciclo completo de
desenvolvimento, com rastreamento de requisitos do documento ao código. Este
tipo de rastreamento envolve a integraçào das modificações no código com algum
sistema de controle de requisitos ou problemas (issue tracker).

Assim, o hook é usado para lançar no sistema de controle de versões quais as
alteraçòes que foram feitas em qual arquivo para qual issue. O fato é que com as
técnicas modernas de desenvolvimento de software, isso está caindo em desuso
pois eleva o custo do desenvolvimento de sistemas sendo que o benefício é
mínimo.

## Onde estão os hooks

Os hooks normalmente estão dentro do diretório .git/hooks, se você tem uma
working tree clonada de um repositório. Nos repositórios _bare_ os hooks estão
no diretório hooks. Ao criar um repositório, este diretório vem com uma série de
arquivos de exemplo que demonstram como escrever seu hook.

Uma coisa muito importante para se ter em mente: todos os scripts foram
projetados para execução em algum shell linux ou unix. Porém você pode escrever
seus hooks em python ou ruby ou na linguagem de scripting da sua preferência.

## Por que você provavelmente não vai usar

A rastreabilidade de _issues_ em código é uma prática considerada antiquada hoje
em dia, principalmente por que engessa o processo de desenvolvimento de
software, tornando-o mais caro. São poucas as empresas que usam essas práticas
pois exigem a adoção de alguma metodologia que exige alto grau de documentação
de todo o processo, como o CMM.

A grande maioria das software houses e empresas que têm serviços de
desenvolvimento não usam tal grau de rastreabilidade e, portanto, não há
necessidade de algo tão apurado. Mesmo no caso de padronizações de comentários,
é mais fácil e rápido confiar no developer do que ter de escrever shell scripts
complexos para validar os comentários.

Assim, provavelmente você não vai usar os hooks, principalmente por que trazem
pouco benefício ao seu dia-a-dia.

# Mais Informações

Se você tem realmente necessidade de criar um hook, vale a pena dar uma lida
[neste artigo](http://git-scm.com/book/pt-br/Customizando-o-Git-Hooks-do-Git). Os
principais hooks estão cobertos e há explicação de qual parâmetro cada um deles
utiliza-se para validar os commits e outras operaçòes do GIT.
