# estudando-git

------------------------------------------------------------------------------------------------------

funçoes do git e o uso das funcionalidades do github no controle e vercionamento

o uso dos termos emprgados em arquivos sera apenas para exemplificar um modelo

link para documentaçao do git https://git-scm.com/book/pt-br/v2

link para video aulas
<br>
https://www.youtube.com/watch?v=kB5e-gTAl_s&t=65s 
<br>
https://youtu.be/Ts8CAuPpmVM

modelo workflow

https://www.alura.com.br/artigos/git-flow-o-que-e-como-quando-utilizar <br>
https://youtu.be/oweffeS8TRc<br> 
https://youtu.be/394mc6PV8t8 <br>
https://youtu.be/HIqyLRKv-YE <br>
https://youtu.be/wzxBR4pOTTs<br>

------------------------------------------------------------------------------------------------------

CICLO DE TRABALHO :
   1°. GIT PULL DA BRANCH PRINCIPAL;<br>
   2°. GERAR NOVA BRANCH APARTIR DA BRANCH PRINCIPAL;<br>
   3°. TRABALHAR E ADICIONAR NOVAS FUNCIONALIDADES NA NOVA BRANCH QUE CRIOU;<br>
   4°. TESTAR E FINALIZAR TRABALHO NA BRANCH TEMPORÁRIA;<br>
   5°. GIT CHECKOUT NA BRANCH PRINCIPAL; <br>
   6°. GIT PULL ;<br>
   7°. TESTAR ANTES DE MERGIAR(UNIR) O CODIGO DA BRANCH TEMPORÁRIA COM A BRANCH PRINCIPAL(TESTAR DEPOIS DE MERGIAR);<br>
   8°. GIT PUSH DA BRANCH PRINCIPAL;<br>
   
------------------------------------------------------------------------------------------------------

 sobre git flow :
   ------------------------------------------------------------------------------------------------------
      O Git Flow é um modelo, uma estratégia ou, ainda, um fluxo de trabalho muito utilizado 
      por equipes de desenvolvimento de software. Ele se destaca por auxiliar na
      organização do versionamento de códigos.

      O Git Flow é recomendado para projetos que utilizam versionamento semântico (semantic versioning) 
      ou que precisam oferecer suporte a várias versões de seu software.

      Segundo o próprio autor, Vincent Driessen, se o projeto exige entrega contínua, 
      como normalmente ocorre em projetos, este modelo não é recomendado para esse tipo de cenário. 
      Porque geralmente com o Git Flow são geradas branches de longa duração e branches de longa duração 
      atrapalham a entrega contínua.

      A utilização do Git Flow também se torna recomendado para projetos que existam uma grande 
      quantidade de pessoas “commitando” dentro de um repositório, ou para projetos que possuem 
      um ciclo de entrega agendada.

      O Git Flow trabalha com duas branches principais, a Develop e a Master, que duram para sempre; 
      e três branches de suporte, Feature, Release e Hotfix, que são temporários e duram até realizar 
      o merge com as branches principais.

      Então, ao invés de uma única branch Master, esse fluxo de trabalho utiliza duas branches principais 
      para registrar o histórico do projeto. A branch Master armazena o histórico do lançamento oficial, 
      e a branch Develop serve como uma ramificação de integração para recursos.

      É ideal que todos os commits na branch Master sejam marcados com um número de versão. 
      Na imagem abaixo, vemos como é a estrutura do fluxo do Git Flow:

         Branch Master/Main
            Principal branch, aqui é onde temos todo o código de produção. Todas as novas funcionalidades 
            que estão sendo desenvolvidas, em algum momento, serão mescladas ou associadas a Master. 
            As formas de interagir com essa branch são através de uma Hotfix ou de uma nova Release.

         Branch Develop
            É a branch onde fica o código do próximo deploy. Ela serve como uma linha do tempo com 
            os últimos desenvolvimentos, isso significa que ela possui funcionalidades que ainda não 
            foram publicadas e que posteriormente vão ser associadas com a branch Master.

         Branch Feature
            São branches utilizadas para o desenvolvimento de funcionalidades específicas. É recomendável 
            que essas branches sigam uma convenção de nome, a convenção mais utilizada é iniciar o nome 
            das branches com feature, por exemplo, “feature/alura-forum”.
            É importante saber que essas features branches são criadas sempre a partir da branch Develop. 
            Portanto, quando finalizada, elas são removidas após realizar o merge com a Branch Develop. 
            Se tivermos dez funcionalidades a serem desenvolvidas, criaremos dez branches independentes.
            importante salientar que as branches de features não podem ter interação com a branch master, apenas com a branch develop.

         Branch Hotfix
            É uma branch criada a partir da master para realizar correções imediatas encontradas 
            no sistema em produção. Quando concluída, ela é excluída após realizar o merge com as branches 
            Master e Develop. Temos uma branch de hotfix para cada hotfix que precisamos implementar!
            A grande diferença entre Feature Branches e Branches de Hotfix é que os Hotfix são criados 
            a partir da Branch Master e quando os finalizamos, eles são mesclados tanto na Branch Master 
            quanto na branch de desenvolvimento. Isso ocorre porque o bug está em ambos os ambientes.
            Além disso, quando fechamos um Hotfix Branch, temos que criar uma tag com a nova versão 
            do projeto. Isso porque cada mudança que fazemos na Branch Master precisa de uma tag que 
            a represente.

         Branch Release
            Uma vez que uma etapa de desenvolvimento esteja concluída, teremos em nossa Branch Develop 
            todas as features e Hotfix mesclados. Então, se quisermos ter todas essas novas funcionalidades 
            na Branch Master, teremos que criar uma Branch de Release.
            A Branch Release serve como ponte para fazer o merge da Develop para a Master.
            Ela funciona como ambiente de homologação e é removida após realizar os testes do merge 
            com a Master. Caso seja encontrado algum bug e haja alguma alteração, ela também deve 
            ser sincronizada com a Develop.
            Por fim, quando fechamos uma Branch Release, 
            temos que criar uma tag com a nova versão de lançamento do software,
            para que possamos ter um histórico completo do desenvolvimento.

<br>

# Padrões de projeto
## Modelo de gestão de equipe: [SCRUM](https://www.youtube.com/results?search_query=scrum+em+9+minutos)
![image](https://user-images.githubusercontent.com/38539884/215773070-7706ac3c-a892-41ac-8c42-0c85b8c12b68.png)


## Workflow: [Git Flow](https://youtu.be/oweffeS8TRc)


![image](https://user-images.githubusercontent.com/38539884/215573408-4d81f256-01c1-47ac-9c16-3400b2112c72.png)

## Clone do projeto
- Faça o clone do projeto e crie uma branch específica para a alteração que está implementando indicando o nome do usuário e o tipo (feature, bugfix, hotfix). 
```
git checkout -b "feature"/"username"/"listar-produtos-estabelecimento"
```
- Crie ou alter o [Diagrama de Classes](https://youtu.be/JQSsqMCVi1k) relacionado.
- Caso a atividade seja especialmente complexa pode-se criar um [Diagrama de Sequencia](https://creately.com/blog/pt/diagrama/tutorial-do-diagrama-de-sequencia/) ou outros.
- Crie [testes unitários](https://pt.wikipedia.org/wiki/Teste_de_unidade).

## Commits [padroniszaçao de comits](https://dev.to/vitordevsp/padronizacao-de-commit-com-commitlint-husky-e-commitizen-3g1n)
- inicie o expediente atualizando a sua branch com a develop.
```
git pull origin develop
```
- faça pequenos commits.
- adicione a referência do gerenciador de projetos. 
```
✨#4598 Cria crud de pessoa 
```
- não esqueça de usar o emoji correspondente a alteração.
- revise as alterações que foram feitas antes de fazer o push.
```
git diff
```
- ao final do dia salve o seu trabalho na sua branch remota.
```
git push origin "feature"/"username"/"listar-produtos-estabelecimento"
```
## Pull Request
- Crie uma PR para a branch develop após concluir uma tarefa (feature/bugfix/hotfix).
- Escolha e adicione o revisor.
  
## [Daily](https://www.ieepeducacao.com.br/daily-scrum) (pode ser virtual)
- Se presencial, no máximo 15 minutos de duração, em pé.
- o que fez ontem?
- o que ira fazer hoje?
- quais os impedimentos impedimentos?
- quais as estratégias?

## Atualize o gerenciador do projeto ([redmine](https://redmine.ati.to.gov.br))
- Use como base o que você fez ontem.
## Modelo de Versionamento: [Versionamento Semantico](https://www.youtube.com/watch?v=K9sSyVsRC7k)

[semver.org](https://semver.org/lang/pt-BR/)

# Úteis
 - instale emojisense no vs code.
 - criem seeds para informações estáticas.
 - verifique seus ultimos commits.
 ```
 git log --oneline
 ```
 - junte commits com históricos irrelevantes.
 ```
 git rebase -i main~3
 ```

## Ferramentas para geração de diagramas 
| Ferramenta | Visual Studio Code | NetBeans |
|:---------------------------|:----------------------------------------------|:----------------------------------------------|
| Drawio | ✔️ | ? |
| :emojisense: | ✔️ | ? |

## Modelos de commits [gitmoji](https://gitmoji.carloscuesta.me/)

| Tipo de confirmação | Emoji | Código |
|:---------------------------|:----------------------------------------------|:----------------------------------------------|
| Alteração em andamento | git commit -m "🚧# " |`:construction:`|
| Correção de erros | git commit -m "🐛# " |`:bug:` |
| Correção crítica | git commit -m "🚑# " |`:ambulance:` |
| Novo recurso | git commit -m "✨# " |`:sparkles:` |
| Arquivos de configuração| git commit -m "🔧# " |`:wrench:` |
| Adicionando dependencia | git commit -m "➕# " |`:heavy_plus_sign:` |
| Removendo dependencia | git commit -m "➖# " |`:heavy_minus_sign:` |
| Documentando o código-fonte | git commit -m "💡# " |`:bulb:` |
| Cosmético | git commit -m "💄# " |`:lipstick:` |
| Metadados | git commit -m "📇# " |`:card_index:` |
| Commit inicial | git commit -m "🎉# " |`:tada:` |
| Desempenho | git commit -m "🐎# " |`:racehorse:` |
| Tag de versão | git commit -m "🔖# " |`:bookmark:` |
| Documentação | git commit -m "📚# " |`:books:` |
| Testes | git commit -m "🚨# " |`:rotating_light:` |
| Adicionando um teste | git commit -m "✅# " |`:white_check_mark:` |
| Passou em um teste | git commit -m "✔️# " |`:heavy_check_mark:` |
| Atualização geral | git commit -m "⚡# " |`:zap:` |
| Melhorar formato/estrutura | git commit -m "🎨# " |`:art:` |
| Refatorar código | git commit -m "🔨# " |`:hammer:` |
| Removendo código/arquivos | git commit -m "🔥# " |`:fire:` |
| Segurança | git commit -m "🔒# " |`:lock:` |
| Atualizando dependências | git commit -m "⬆️# " |`:arrow_up:` |
| Fazendo downgrade das dependências | git commit -m "⬇️# " |`:arrow_down:` |
| Tradução | git commit -m "👽# " |`:alien:` |
| Texto | git commit -m "✏️# " |`:pencil:` |
| Deploy | git commit -m "🚀# " |`:rocket:` |
| Move/rename repository | git commit -m "🚚# " |`:truck:`|
| Mudança na revisão do codigo | git commit -m "👌# " |`:ok_hand:`|
| Revertendo mudanças | git commit -m "⏪# " |`:rewind:`|
| Mudanças rápidas | git commit -m "💥# " |`:boom:`|
| Merging branches | git commit -m "🔀# " |`:twisted_rightwards_arrows:` |
| Docker | git commit -m "🐋# " |`:whale:` |
