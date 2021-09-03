
---
title: "Engenharia de Software I"
---

# Diagrama de Classes
- Um **diagrama de classes** descreve os tipos de objetos no sistema e os vários tipos de relacionamentos estáticos que existem entre eles.
	- Diagrama Estrutural
	- Pode ser gerado código a partir dos casos de uso e diagramas de classes
- As classes representam as **propriedades e o comportamento** de um conjunto de objetos em um sistema
	- Abstrações do mundo real
- Este diagrama mostra quais são as classes do sistema, seus atributos, suas operações e a relação entre as classes
## Classes
- A classe é o principal elemento de uma modelagem OO.
- As classews auxiliam na **modelagem conceitual** e no **mapeamento da modelagem para o código** de programação.
	- É possível gerar código automático
- Uma classe possui três seções: nome, atributos, métodos.
  ![[Pasted image 20210818172442.png]]
### Exemplos de Classes

![[Pasted image 20210818173004.png]]
![[Pasted image 20210818173016.png]]
![[Pasted image 20210818173024.png]]
![[Pasted image 20210818173445.png]]
![[Pasted image 20210818173457.png]]
![[Pasted image 20210818173513.png]]
### Visibilidade dos Membros da Classe

Para especificar a visibilidade dos membros da classe, utiliza - se os simbolos abaixo, antes do nome do membro:
- **+**: Public
- **-**: Private
- **#**: Protected
- **Sem modificador**: Package
-
### Associação
- As associações representam as **relações entre as ocorrências das classes**
	- Relacionamento estrutural e estático entre as classes
- Associações em um diagrama de classe definem os **tipos de ligações que os objetos participam**
- As Associações podem ter nomes
	- Existe um sentido padrão de leitura
	- Seta de Leitura
		- Se não houver, ler da esquerda pra direita e de cima pra baixo
	- Visibilidade das associações
### Multiplicidade
- É a indicação de quantos objetos podem participar de um relacionamento
	- **1**: Exatamente um objeto
	- **0..1**: Zero ou Um objeto
	- **\***: Zero ou Mais objetos

## Agregação
- Relação de dependência entre duas classes
- Descrição de um **relacionamento todo-parte ou "parte de"**, também conhecido como um relacionamento do tipo *has-a*.
- É um caso particular de associação
	- Objetos de mesma natureza (transação ou físico)
	- Ex.: Departamento e Professores

- Não denota exclusividade
![](../Pasted%20image%2020210824110504.png)

- Tipo de relacionamento que **não força a destruição do conjunto**, ou seja, **uma vez destruído o projeto todo, não há obrigatoriedade da destruição do objeto parte**.

## Composição

- Descrição de um **relacionamento todo-parte ou "parte de"**, também conhecido como um relacionamento do tipo *has-a*.
- Nessa caso, o **o objeto pertence a somente UM objeto todo**, ou seja, denota exclusividade.
- As partes não podem existir sem o todo
![](../Pasted%20image%2020210824111703.png)
- Do lado do todo a multiplicidade não pode ser maior do que 1

### Papel
- É uma descrição para a associação
- Como a agregação e a comosição são casos particulares da associação, elas também podem ser rotuladas por papeis
![](../Pasted%20image%2020210824112840.png)
- O nome da estrutura de dados é o mesmo nome do papel
![](../Pasted%20image%2020210824113003.png)

## Generalização
- É um relacionamento onde temos uma classe ancestral e outras classes herdadas
- O subtipo deve incluir todos os elementos (atributos, operações e associações) do supertipo.
- Na implementação física corresponde a um processo de herança.
![](../Pasted%20image%2020210824113313.png)
- Devem ser representações estruturais definitivas

### Herança Múltipla

- Múltiplas superclasses para uma mesma subclasse

### Classes Associativas
- Permite acrescentar atributos, operações e outras características às associações
![](../assets/Pasted%20image%2020210825161138.png)
![](../assets/Pasted%20image%2020210825161207.png)

### Associação Recursiva ou Reflexiva

![](../assets/Pasted%20image%2020210825161609.png)

### Associação Qualificada
- Uma associação 1..N pode virar 1..1

![](../assets/Pasted%20image%2020210825162035.png)
- Quando há um tipo um pra muitos, onde o muitos tem um identificador único, pode virar 1 pra 1

![](../assets/Pasted%20image%2020210825162212.png)

## Esteriótipos de Classes

- **Boundary**: Interfaces (UI)
- **Entity**: Dados que serão persistidos (todas as vistas até então)
- **Control**: Tratamento de Evento

# Diagrama de Pacotes

- Geralmente, os pacotes são usados para **agrupar classes**
	- Agrupamento lógico dependência
	- Ex.: Domínio, Interface, Persistência, Utilitários, Controles, etc.
- Pacotes também podem agrupar outros elementos da UML
- Usados para:
	- Definição de arquitetura de software
	- Evidenciam acoplamento nos projetos
- Cada classe é **membro de um único pacote**
	- A não ser que ela esteja em um **pacote aninhado**

> Basta uma classe de um pacote importar uma classe de outro para existir dependência entre eles

- Um pacote pode conter classes e subpacotes

## Dependência entre Pacotes
- Existe dependência entre dois elementos de **alterações na definição de um** elemento (o fornecedor) pode **causar alterações no outro** (o cliente).
- São indicadas pela seta pontilhada

# Padrões de Projeto

## Fachada

Nos pacotes, as classes podem ser:
- **Públicas**: Parte da interface do pacote pode ser usada e importada por classes de outros pacotes
- **Privadas/Packages**: São escondidas para as classes de outros pacotes

> Se o pacote tem apenas **uma classe pública**, ela é a fachada do pacote.


Uma fachada pode:
- Tornar uma biblioteca mais fácil de entender e usar
- Tornar o código que utiliza esta biblioteca
- Reduzir as dependências, trazendo flexibilidade no desenvolvimento do sistema
- Envolver uma interface mal desenhada em uma melhor definida.

# Diagrama de Sequência

- Daigrama Comportamental: Busca ilustrar coisas que acontecem no sistema em tempo de execução
- Descreve a maneira como os grupos de objetos colaboram em algum comportamento ao longo do tempo
- Registra o comportamento de um caso de uso/cenário exibindo as mensagens passadas entre os objetos
	- Temos N diagramas de sequência para cada caso de uso
- As interações são ilustradas a partir de **operações ou métodos**
- Construído a partir do diagrama de casos de uso
	- Depende do diagrama de classes
- Ênfase na ordenação temporal em que as mensagens são trocadas entre os objetos de um sistema
- Identificação de Operações
	- Quando criados a partir de casos de uso
	- Eventos e respostas do sistema

## Elementos do diagrama de sequências
- Participantes (objeto, atores, e outros papeis)  possuem uma linha da vida vertical (lifetime)
- A dimensão vertical é a sequência onde a vida do objeto durante a interação é representada
![](../assets/Pasted%20image%2020210825171235.png)
- Devem modelar a forma como os participantes interagem, e não a lógica de controle
- Os loops, alternativas e condições usam frames, que marcam uma parte do diagrama.
![](../assets/Pasted%20image%2020210825172010.png)

### Diagramas de Caso de Uso x Sequência

- Casos de Uso: Visão Externa do Sistema
- Sequência: Descrevem como casos de uso são realizados.
- Os objetos são instâncias nomeadas ou anônimas de classes, mas também podem representar instâncias de outros itens, como por exemplo, componentes
- Os diagramas de sequência são utilizados para ilustrar a visão dinâmica de um sistema

# Testes de Software

- Verificam se um programa apresenta um resultado esperado, ao ser executado com alguns casos de teste
	- Comportamento de uso comum é útil para testar se o sistema funciona como deveria
	- Comportamento anômalo de uso é útil para testar se o sistema é tolerante a falhas (possui erros e como trata as exceções)

## Objetivos

### Testes de Validação
Verifica se o software atende a seus requisitos
- Pelo menos um teste para cada requisito
- Requisitos Testáveis

### Testes de Defeito
Descobre situações de comportamentos indesejados do sistema
- Não precisam refletir o uso comum do sistema
- Maior parte dos defeitos encontram - se no uso incomum

- **Defeito ou Bug**: Erro no código
-  **Falha**: Erro na execução, pode ser causada por um bug ou mais

## Verificação x Validação

- **Verificação**: estamos construindo o produto de maneira correta?
	- Feita pelos desenvolvedores
	- Atende seus requisitos
- **Validação**: estamos construindo o produto certo?
	- Feito pelo cliente
	- Requisitos podem falhar

## Testes x Revisão Técnica

- Um processo de revisão pode ser definido como uma avaliação crítica de um objeto (requisitos, modelos, códigos e testes)
- Revisão e Inspeção são técnicas estáticas (não precisa executar o software)

- Revisões e Inspeções técnicas são mais eficazes na detecção de defeitos (60% à 90%)
- Testes são importantes para complementar revisões e aferir o nível de qualidade conseguido

### Vantagens

- Durante testes, erros podem mascarar outros erros
- Uma sessão de revisão pode encontrar vários erros
- Versões Incompletas de um sistema podem ser inspecionadas sem custos adicionais
	- Não necessita de estruturas temporárias
- Além de Defeitos, inspeções podem avaliar atributos de qualidade de software
	- Padrões, manutenabilidade, reusabilidade,...
		- Maior produtividade
		- Menores Custos

## Visão Geral

- Teste exaustivo é geralmente impossível
- Inviável testar todo o sistema (complexidade ciclomática > 50)
- O projeto de testes procura encontrar testes que:
	- Tenham a mais alta probabilidade de descobrir defeitos
	- Com o mínimo esforço
	- Quanto maior o risco, maior a quantidade de testes
	- Limitações: Cronograma e Orçamento

## Modelo do Processo de Testes
- Casos de Teste
- Dados de Teste
	- Geração automática/manual de "Dados de Teste"
- Resultados de Teste
- Relatórios de Teste

## Quantidade de Testes de Software

- Estabelecer um nível de confiança do software para o seu propósito
	- Finalidade do Software
	- Expectativa de Usuários
		- O usuário aceita sistemas novos falhos, mas sistemas maduros não
	- Ambientes de Marketing

## Métodos de Testes

- Evitar testes irreprodutíveis e improvisados
	- Durante e após a realização dos testes, resultados devem ser inspecionados
	- Comparando - se resultados previstos e obtidos
	- Os resultados devem ser registrados em relatório
	- Importante para fazer teste de regressão posteriormente
- Os desenvolvedores nem sempre são adequados para testar seus próprios produtos
	- Autores têm maior dificuldade em enxergar problemas
	- Trabalho de testadores independentes é importante no caso de testes de acetação
	- Os testes são **indicadores de qualidade do produto**
	- Quanto maior o número de defeitos detectados maior o número de defeitos não detectados
	- Número anormal de defeitos em uma bateria de testes
		- Necessidade de redesenho dos itens testados
		- Pode ser melhor refazer do que consertar
		- Pode ser necessário rever o projeto de testes

## Técnicas de Teste

### Método de Caixa Branca

**Objetivo**: Determinar defeitos na estrutura interna do software (baseado no código fonte)
- Utiliza o projeto de testes que exercitem os possíveis caminhos de execução
- Casos de teste que cubram todas as posibilidades do programa
- Quase todas as variações originadas por estruturas de condições são testadas

#### Aplicável Em
- Testes de Unidade
- Testes de Integração
- Testes de Regressão
- Testes de Sistema

### Método de Caixa Preta
**Objetivo**: Determinar se os requisitos foram total ou parcialmente satisfeitos pelo software

- Não verificam como ocorre o processamento, mas apenas o resultado produzido
- Verificar se o resultado gerado pelos testes está de acordo com o esperado
- São levados em consideração todos os eventos que podem ser disparados pelo usuário

### Método de Caixa Cinza
- O desenvolvedor dos testes não têm acesso ao código fonte da aplicação, porém:
	- Tem conhecimento dos algoritmos que foram implementados
	- Poed efetuar manipulações em arquivos de entrada e saída do tipo XML
	- Pode fazer acesso ao banco de dados da aplicação
	- Alguns atores definem a caixa-cinza como o **teste de integração**
	- O sistema é visto até o nível de módulo, mas o interior dos módulos não são vistos

## Ganularidade dos Tipos de Teste

![](../assets/Pasted%20image%2020210829131518.png)

### Testes Unitários

- Testes automatizados de pequenas unidades do sistema (normalmente, classes ou funções)
- Quando a unidade testada é um objeto, devem ser cobertas as reguintes características:
	- Testar todos os métodos
	- Definir e verificar o valor de todos os atributos
	- Colocar o objeto em todos os estados possíveis
		- Diagrama de estado UML

- Pode ser caixa preta ou caixa branca

#### Escolha de Casos de Teste

Devem ser escritos dois tipos de casos de teste por unidade:
- **Refletir o funcionamento normal**: Mostrar que o comportamento testado é funcional em circunstâncias comuns
- **Entradas Anormais:** Mostrar que sistema processa entrada anormais sem falhar
	- Ex.: Valores negativos, valores muito grandes, tipos de valores diferentes..stc
		- Testes baseados em diretrizes
		- Testes de partição de equivalência

#### Anatomia

- Cada classe testada possui uma classe de teste. Por convenção o seu nome deve acabar com Test
- Anotação @Test
- Nome deve começão com a palavra *test*
- **Fixture**: Contexto do teste
- Chamada do método sob teste
- **Assert**: Verifica se o resultado é aquele esperado
- **@Before**: Executa antes dos métodos *@Test*
- Cada método executa em uma instância diferente da classe de teste

#### Benefícios
- Detectar bugs na fase de desenvolvimento
- Documentação: É possível entender o comportamento de um código por meio dos testes e é porta de entrada para novos desenvolvedores de um código

#### Princípios FIRST

- Rápidos
- Independentes (ordem não é importante)
- Determinísticos (Repetíveis)
- Auto - verificáveis
- Timely (escritos o quanto antes)

#### Cobertura

(número de comandos executados pelo teste) /( total de comandos do programa)
- O ideal é pelo menos 60%