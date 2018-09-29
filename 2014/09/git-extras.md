# Git Extras
**Ronaldo Faria Lima**

Aqui estão alguns conceitos importantes que não foi possível cobrir na última palestra sobre GIT.

## O repositório é sempre local

Ao contrário do SVN que obriga você a trabalhar com um repositório remoto, o GIT sempre usa um repositório local, mesmo que você tenha obtido a sua árvore de código de um servidor remoto. A árvore remota é obtida pelo comando clone, que faz o que o nome diz: cria um clone, ou uma cópia, do repositório remoto na sua máquina local.

Isso tem implicações interessantes. Sempre que você faz um commit, que é a operação na qual você registra suas alterações no repositório, você está fazendo isso, obrigatoriamente, no repositório local. É isso mesmo: você não altera o repositório remoto. Para alterar o repositório remoto é necessário usar o comando push.

Ou seja, faça commit sem medo de ser feliz! Na pior das hipóteses, basta apagar a sua árvore de código juntamente com o seu repositório local e mandar baixar tudo de novo com um novo comando clone. Essa característica lhe dá a chance de pensar duas vezes antes de publicar as suas alterações em um repositório compartilhado ou no repositório de outra pessoa.

## Faça commits regularmente

Ao invés de escrever um montão de código para só depois integrar ao repositório, use o princípio do "faz um pouquinho, comita um pouquinho". Realizar commits regularmente permite que você controle melhor o seu desenvolvimento, permitindo que você possa voltar atrás sempre que quiser.

Assim, fica mais fácil para você desfazer alterações ou refazer alterações que havia feito sem muita dor-de-cabeça. Ou seja, siga a recomendação de quem fez a ferramenta: faça quantos commits quiser, mas sempre commits pequenos. Isso ajuda o seu trabalho controlando melhor as suas alterações.

## Use Topic Branches

O topic branch é um branch cuja existência é temporária, segundo a conceituação de quem escreveu a ferramenta. Falando em bom português, é o branch do programador. Ou seja, sempre que for desenvolver algo, crie um branch para si e trabalhe neste branch.  Não importa se você está trabalhando em uma correção de defeito ou na criação de uma nova característica. Isso permite que você tenha mais liberdade para desenvolver e, também, permite que o seu trabalho ocorra de forma independente.

O merge é natural no GIT. Cedo ou tarde você vai fazer um merge. A ferramenta foi feita para isso. Escrever suas alterações em branches não só facilita sua vida como a de outras pessoas que trabalham com você. Além disso, isolam suas alterações permitindo que sua equipe possa avaliar o que você fez e aprender com o seu código.

## Use ferramentas gráficas

Apesar de ser um cara old school e de ter demonstrado a operação do GIT usando linha de comando, procure usar ferramentas gráficas. Existem diversos clientes gráficos para GIT que funcionam muito bem e que lhe dão uma grande produtividade. A principal vantagem da ferramenta gráfica é a possibilidade de apresentar diferenças e logs de forma visual, o que facilita a sua vida.

Apesar disso, não se esqueça que a linha de comando é a sua salva-guarda. Apesar das ferramentas gráficas fazerem quase tudo, as limitações impostas por elas são resolvidas na linha de comando. Porém, no dia-a-dia, uma ferramenta gráfica é o ideal tendo a produtividade em mente.

## Saiba quem é o culpado

Você consegue saber quem fez alterações no código através do comando blame. Este comando permite visualizar quem alterou cada linha de código, qual o commit na qual aquela linha de código foi publicada e quando isso aconteceu. Assim, você pode procurar o sujeito que escreveu aquele trecho de código que beira a magia negra.

## Identifique-se!

O GIT permite que você configure sua identidade de maneira muito simples. Se você usa uma ferramenta gráfica, veja nas preferências da mesma as informações de usuário e email. Estas informações são salvas em cada commit para identificar quem fez o que.

Se você estiver usando a linha de comando, pode usar a seguinte sintaxe:

	$ git config --global user.name "Ronaldo Faria Lima"
	$ git config --global user.email "ronaldo@ronaldolima.eti.br"

Obviamente que será necessário que você informe seu nome e e-mail corretos. Este exemplo demonstra como alterar de forma global os ajustes. Isto quer dizer que qualquer repositório que você crie ou clone usará estas informações de usuário.

Porém, suponha que você queira identificar-se de maneira diferente para determinado projeto. Algumas empresas costumam dar a freelancers e terceiros endereços de e-mail para comunicação interna no intuito de controlar melhor as comunicações. Digamos que eu estivesse trabalhando em um projeto específico para a Formaweb e que eles me dessem um endereço de email especificamente para trabalhar neste projeto. Você pode alterar as características somente do repositório do projeto.

Para tanto, basta ir até a árvore do repositório e executar o seguinte comando:

	$ git config user.email "ronaldo@formaweb.com.br"
