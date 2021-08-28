# Capítulo 1

**Redes de Computadores** são um conjunto de computadores autônomos interconectados por uma única tecnologia. Onde a conexão é definida como **troca de informações**. Ou seja, na Rede, usam - se diversos computadores, onde os hardwares e sistemas operacionais distintos são visíveis ao usuário.

**Sistemas Distribuídos** são redes de computadores mas, para o usuário, parece ser um único sistema concorrente. Essa ilusão é criada por meio de um middleware. Ou seja, o sistema distribuído se baseia no software, abstraindo diferentes hardwares e sistemas operacionais do usuário.

> Ex.: WWW (World Wide Web):
	> - Trabalha em cima da Internet
	> - Usa o modelo de Documento (Página da Web)

> **Lei de Metcalf**: O valor da rede é proporcional ao quadrado do número de usuários.

## Modelo Cliente - Servidor
![[Pasted image 20210811120728.png]]

## Modelo Peer-to-Peer
Indivíduos se comunicam com outros indivíduos e a maioria não possui Banco de Dados central.

![[Pasted image 20210811120826.png]]

## Exemplos de Tecnologias

- **RFID (Radio Frequency Identification)**: Chips passivos (sem bateria)
- **NFC (Near Field Communication)**: O dispositivo pode atuar como um RFID


## Tipos de Tecnolgias de Transmissão (aka Enlace)

### Ponto a Ponto

Conectam pares de máquinas individuais, onde os pacotes de informações enviadas talvez tenham que passar por máquinas intermediárias. É muito importante encontrar boas rotas.

### Broadcast

Possui apenas um canal de comunicação. Os pacotes enviados por qualquer máquina podem ser recebidos por todas as outras

> Os pacotes contém um campo de endereço que especifica seu destino.
> Ex.: Rede sem Fio

O brodcats pode ser dividido em duas subcategorias.

#### Alocação Estática

O tempo é dividido em intervalos discretos e utiliza - se um algoritmo de rodízio, fazendo com que cada máquina transmita apenas no intervalo que dispõe.

#### Alocação Dinâmica

Essa ainda pode ser dividida em mais duas categorias

##### Alocação Dinâmica Centralizada

Apenas uma entidade determina quem transmitirá em seguida

##### Alocação Dinâmica Descentralizada

Não existe entidade central, ou seja, cada máquina deve decidir por si só se a transmissão deve ser realizada.

## Tipos de Classificação

### Classificação por escalabilidade

![[Pasted image 20210811121438.png]]

#### PAN (Personal Area Network)

Composta pelos dispositivos ao alcance de uma pessoa, como um computador e seus periféricos. Funciona em um paradigma mestre-escravo.

> Tecnologias Importantes: Bluethoot, RFID

#### LAN (Local Area Networks)

Se aplica dentro e próximo a um único prédio, onde os padrões são:
- Sem Fio: IEEE 802.11 (Wi-FI)
- Com Fio: Vários padrões diferentes

No pior caso, o tempo de transmissão é limitado e conhecido com antecedência.

Em termos de **performance**, as LANS com fio são melhores em todas as dimensões, por ser mais fácil enviar informações por um fio ou fibra ao invés do ar.

O enlace é ponto - a - ponto.

> Ex.: IEEE 802.3: Ethernet

LAN sem fio:

![[Pasted image 20210811122350.png]]

LAN com fio:

> Os **Switches** funcionam em loop. É trabalho do protocolo descobrir o caminho dos pacotes.

![[Pasted image 20210811122422.png]]

#### MAN (Metropolitan Area Network)

Sua área abrange uma cidade.

> Ex.: Redes de TV a Cabo

![[Pasted image 20210811123750.png

#### WAN (Wide Area Network)

Abrange uma área geográfica frequentemente comparável a um país ou continente.

As Sub-Redes têm a função de transportar mensagens entre os hosts. É uma coleção de linhas de comunicação de dados e roteadores, e são compostas por:
- **Linhas de Transmissão**: Transportam bits entre as máquinas.
- **Comutadores (Roteadores)**: Computadores especializados que conectam 3 ou mais linhas de trnasmissão.

Muitas WANs são **redes interligadas**, pois os roteadores conetarão diferentes tipos de tecnologia de rede.

O operador da sub-rede (chamado de **ISP (Internet Service Provider**) também se conecta a outras redes que fazem parte da internet.

![[Pasted image 20210811145003.png]]

**Algoritmo de Roteamento** é o processo em que o roteador toma a decisão sobre qual caminho usar e onde enviar o pacote.

#### Redes Interligadas

Uma **Rede Interligada** é formada pela combinação de sub-redes e seus hosts.

No cotidiano, a conexão entre uma LAN e uma WAN ou entre duas LANs é o modo normal de se formar uma rede desse tipo.

> No geral, se a tecnologia subjacente pe diferente em partes distintas, provavelmente temos uma rede interligada.


**Gateway**: Máquina que faz conexão entre duas ou mais redes e oferece a conversão necessária.

## Hierarquia de Protocolos

As redes são organizadas como uma plilha de **camadas** onde o objetivo de cada camada é oferecer determinados serviços às camadas superiores.

**Protocolo**: Acordo entre as partes que se comunicam, estabelecendo como se dará a comunicação.

As entidades que ocupam cada uma das camadas são chamadas de pares ou **peers** e cada camada transfere os dados e as informações de controle para a camada imediatamente abaixo dela.

![[Pasted image 20210811150729.png]]

**Interface**: Existe entre cada par de camadas adjacentes e define as operações e serviços que a camada inferior tem a oferecer à camada acima.

**Arquitetura de Rede**: Conjunto de camadas e protocolos

![[Pasted image 20210811151054.png]]

Códigos de **detecção e/ou correção** de erros são usados em todas as camadas.

**Controle de Fluxo**: Impedir que um transmissor envie muitos dados e cause um **congestionamento** na rede.

## Serviço Orientado a Conexões

Se baseia no sistema telefônico. O usuário estabelece uma conexão, utiliza e depois libera. **Circuito** é  o nome dado a uma conexão com recursos associados e largura de banda fixa.

## Serviço Não Orientado a Conexões

Se baseia no sistema postal. Cada mensagem carrega um endereço e são roteadas pelos nós intermediários através do sistema.

**Pacote**: Mensagem na camada de rede.

- **Comutação store-and-forward**: Quando os nós intermediários recebem uma mensagem completa antes de enviá - la.
- **Comutação cut-through**: Quando a transmissão de uma mensagem em um nó começa antes de ser completamente recebida.

A confirmação de mensagens introduz overhead e atrasos, que normalmente compensam, mas às vezes são indesejáveis.

- **Sequência de Mensagens**: Os limites das mensagens são preservados. Se enviadas duas mensagens de 1024 bytes, chegarão como duas mensagens, e não como uma mensagem de 2048 bytes.
- **Fluxo de Bytes**: As mensagens não tem limite. Se chegam 2048 bytes, não é possível distinguir se foram 2 de 1024 ou 2024 de 1 byte.

> Em resumo os serviços podem ser:
> - Orientado a Conexões ou
> - Não orientado a Conexões e
> - Confiável (com confirmação) ou
> - Não confiável

**Datagramas**: Serviços não orientados a conexões e não confiáveis.

**Serviço de Datagramas Confirmados**: Envia uma mensagem e recebe confirmação de recebimento

**Solicitação/Resposta**: Envia um único diagrama contendo a solicitação, a resposta contém a réplica.

![[Pasted image 20210811153933.png]]

## Primitivas de Serviço

Um serviço é especificado por **primitivas** disponíveis para que os processos do usuário ecessem o serviço.

Um serviço é comop um objeto ou um tipo de dados abstrato em uma linguagem orientada a objetos. Ele define as operações que podem ser executadas sobre um objeto, msa não especifica como essas operações são implementadas.
O protocolo se refere à implementação do serviço.

# Capítulo 3

**Camada de Elance de Dados**: Responsável pela comunicação confiável entre computadores adjacentes (ordem de envio dos bits é preservada)

A comunicação pode indtroduzir erros dependendo do meio utilizado

- Taxa de Transmissão Limitada: Envio de um conjunto de bits demora um tempo para ser transmitida.
- Tempo de Propagação: O tempo que leva dos bits da origem ao destino

## Questões Relacionadas com Projeto

- Definição do Formato da PDU de Enlace (Quadros)
- Tratamento de Erros
- Controle de Fluxo: Controle no fluxo de quadro enviados (impedir congestionamento)

## Serviços Oferecidos para a Camada de Rede

![[Pasted image 20210812161345.png]]

### Três Tipos de Serviços

- Sem Conexão, Não Confirmado
	- Quadros perdidos são ignorados (recuperação feita pela camada superior)
	- Adequado para meios com baixa taxa de erros
- Sem Conexão, Confirmado
	- Quadros recebidos corretamente são confirmados
	- Uso de temporizadores
	- Adequado para meios com taxas de erro elevadas
- Com Conexão, Confirmado
	- Oferece um serviço como um fluxo de bits confiável para a camada de rede
	- Estabelece a conexão -> Transfere os Dados -> Encerra a Conexão
	- Adequado para enlaces longos e não confiáveis (transmissor e receptor muito longes)

## Formato do Quadro

- **Quadro**: Únidade Mínima de Envio da Camada de Enlace de Dados

- Quadro = Dados + Informações de Controle (endereço, verificação de erros, etc)

![[Pasted image 20210812163417.png]]

Uma das responsabilidades do cabeçalho: identificar onde começa e onde termina cada quadro. O cabeçalho também faz parte do quadro.

- Contagem de Caracteres
	- Problema do Erro em Cascata: Se o caractere no cabeçalho tem erro, terá erros em toda a leitura.

![[Pasted image 20210812163627.png]]

- Inserir caracteres especiais de início e fim (FLAG)
	- Tratamento de casos especiais com o caractere ESCAPE
	- Técnica chamada de character stuffing
	- Na recepção de 2 ESC consecutivos, 1 é descartado
	- Usado em protocolos orientados a caractere

![[Pasted image 20210812164101.png]]

- Inserir flags de início e fim
	- Ideia similar a anterior para protocolos orientados a bit

- Flag: 01111110
	- TX insere um 0 sempre que transmite uma sequência de cinco 1's
	- RX ao receber requência de cinco 1's seguida de 0, descarta o 0
	- Técnica de Bit Stuffing
	- Usado pelo USB (Universal Serial Bus)

![[Pasted image 20210812164430.png]]

- Usar violação de código de camada física
	- Usar sequência de bits inválida da técnica 4B/5B da camada fśiica para definir a flag
	- Ethernet e 802.11 utilizam uma combinação de métodos
	- É comum o uso de um preâmbulo longo

- Controle de Erros

**Objetivo**: Repassar os dados recebidos da camada física corretamente, em ordem e sem repetição para a camada de rede.

**Mecanismos Utilizados**

- Confirmação positiva e/ou negativa dos quadros recebidos pelo destinatário
- Temporização dos quadros enviados pela origem (timeout)
- Retransmissão do quadro um número finito de vezes
- Utilização de número de sequência para os quadros enviados


- Controle de Fluxos

**Objetivo**: Evitar o congestionamento

**Ideia Geral**: Mecanismo de realimentação que permita que o TX conheça o estado do RX; Redes de alta velocidade: controle das fontes de tráfego

**Comentários sobre as questões de projeto**

- Algumas dessas questões aparecem em outras camadas
- Solução adotada depende da camada, protocolo e aplicação

# Capítulo 4

## Subcamada de Acesso ao Meio

- Tudo que foi visto no capítulo anterior foi em relação a comunicação ponto a ponto = canal dedicado
- Parte da camada de enlace de dados responsável pelo controle de acesso ao canal de comunicação
	- Evita ao máximo que haja interferência
	- Evitar que mais de um nó se comunique ao mesmo tempo e gere conflitos
	- Redes de Broadcast
	- Difusão, compartilhado ou de acesso aleatório
- Presente nas redes locais
- Problema
	- Como alocar um canal de difusão único para vários usuários?
	- Protocolo de Acesso: Define quem terá direito a utilizar o canal de comunicação
- Solução: Algoritmos de Alocação
	- Alocação Estática
	- Alocação Dinâmica

## Alocação Estática

- FDM ou TDM
	- FDM (estações de rádio, canais de TV) é a forma tradicional quando existe um número muito pequeno de usuários e tráfego de cada usuário é pesado
	- Transmissão Contínua
- Em Redes de Computadores
	- Número de estações é grande e variável com o tempo
	- Tráfego é do tipo rajada
	- Desperdício de banda

## Alocação Dinâmica

Premissas da alocação dinâmica:
- Estações com tráfego independentes
	- N estações independentes que geram quadros a serem transmitidos
	- Estação fica bloqueada até terminar a transmissão do quadro

- Canal de comunicação único
	- Todas as estações compartilham o canal para TX e RX
	- Equivalentes (HW), podendo ter prioridades (SW)
	- Hardwares Equivalentes
	- Mesmo meio e mesma frequência

- Colisões
	- Transmissão simultânea de 2 ou mais quadros por estações diferentes
	- Estações são capazes de detectar colisões
	- Quadros em colisão devem ser retransmitidos

- Sistema de Contenção
	- Sistema no qual vários usuários compartilham um canal comum de tal forma que pode levar a conflitos
- Abordagens
	- Política de Transmissão de Quadros
		- A qualquer instante (tempo contínuo)
		- Em momentos (slots) pré - determinados (tempo discreto)
			- A Transmissão começa no início do slot e termina ao fim
			- Requer sincronização de relógios

	- Detecção de Portadora (carrier sense): Detectar se o canal está livre
		- Sem detecção
		- Com detecção

## Aloha

**Princípio Básico**:Tansmita na hora que tiver dados a enviar.
- Haverá colisões, detectadas pela escuta do quadro devolvido por broadcast
- Retransmissões após tempo aleatório para minimizar chances de novas colisões (random back-off)

![[Pasted image 20210817132005.png

### Slotted Aloha

Tempo DIscretizado
	- Dividir o tempo em intervalos, onde cada intervalo corresponde a um quadro. 
	- Transmissões só podem ocorrer no início dos intervalos
	
- Uma Estação é responsável pelo sincronismo
- Alcança o dobro de utilização do canal (throughput)
	- Compara o atraso do ALOHA original com o Slotted ALOHA em carga baixa. Qual deles é menor?

![[Pasted image 20210817132254.png]]