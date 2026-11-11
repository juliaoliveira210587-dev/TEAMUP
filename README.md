# **TEAMUP — Sistema de Gestão de Campeonatos**

## **1. Apresentação do projeto**

O **TeamUp – Arena Gamer** é um projeto acadêmico de gerenciamento de campeonatos, desenvolvido em Portugol utilizando o ambiente VisualG.

O sistema foi criado para auxiliar na organização de competições em uma Arena Gamer, oferecendo três modalidades: **corrida de carros, futebol e basquete**.

O programa utiliza conceitos de lógica de programação para cadastrar participantes e equipes, registrar resultados, calcular pontuações, apresentar classificações e identificar os campeões.

Além disso, conta com o **Hall da Fama**, que permite registrar e consultar os vencedores de cada modalidade após a conclusão dos campeonatos.

## **2. Funcionamento geral do sistema**

Ao iniciar o programa, o usuário encontra um menu com as modalidades disponíveis:

- Corrida de carros;
- Futebol;
- Basquete;
- Hall da Fama.

Cada modalidade possui suas próprias opções de cadastro, registro de resultados e consulta de classificações.

### **Corrida de carros**

O campeonato é organizado em quatro rodadas. O usuário registra as pontuações dos participantes em cada rodada, e o sistema calcula a pontuação total e apresenta a classificação final.

### **Futebol**

O sistema permite cadastrar equipes e registrar os resultados das partidas, considerando os placares do primeiro e do segundo tempo.

Quando necessário, também permite registrar uma disputa por pênaltis.

A classificação é calculada de acordo com os resultados registrados.

### **Basquete**

O sistema permite cadastrar equipes, registrar os resultados das partidas e acompanhar a classificação.

### **Hall da Fama**

O Hall da Fama permite registrar o campeão de cada modalidade após a conclusão da competição.

Após o registro do campeão, o campeonato correspondente fica encerrado para novos resultados e cadastros, mas as informações continuam disponíveis para consulta enquanto o programa estiver aberto.

Os dados são armazenados temporariamente durante a execução do VisualG.

## **3. Explicação das principais partes do código**

### **3.1 Identificação do algoritmo**

O programa foi desenvolvido em Portugol e utiliza a estrutura de algoritmos do VisualG.

O comando `algoritmo` identifica o programa, enquanto `inicio` e `fimalgoritmo` delimitam sua execução.

### **3.2 Declaração de variáveis**

O TeamUp utiliza variáveis para armazenar informações como nomes, pontuações, resultados e opções selecionadas.

Os principais tipos de dados utilizados são:

- **Caractere:** armazena nomes e outras informações em texto.
- **Inteiro:** armazena números, como pontuações e quantidades.
- **Lógico:** representa condições verdadeiras ou falsas.

### **3.3 Utilização de vetores**

Os vetores permitem armazenar diferentes informações relacionadas aos participantes e às equipes.

Por exemplo, podem ser utilizados para guardar nomes e pontuações de vários participantes, facilitando o cálculo e a apresentação das classificações.

### **3.4 Inicialização dos dados**

No início da execução, o sistema prepara as variáveis e os registros necessários para o funcionamento dos campeonatos.

Essa etapa permite iniciar os controles de participantes, resultados e pontuações.

### **3.5 Estruturas de repetição**

O programa utiliza estruturas de repetição, como `para` e `repita`, para executar operações várias vezes.

Essas estruturas auxiliam na navegação pelos menus, no processamento dos resultados e na consulta dos participantes.

### **3.6 Configuração das modalidades**

O sistema possui três modalidades, cada uma com regras específicas.

Na corrida, são registradas as pontuações de quatro rodadas.

No futebol, são considerados os placares dos dois tempos, com possibilidade de disputa por pênaltis.

No basquete, os resultados das partidas são utilizados para calcular a classificação.

### **3.7 Menu principal**

O menu principal permite selecionar a modalidade desejada ou acessar o Hall da Fama.

A navegação utiliza comandos como `escreval`, para apresentar informações, e `leia`, para receber a opção escolhida.

### **3.8 Cadastro de participantes e equipes**

O sistema permite registrar os participantes ou equipes das competições, de acordo com a modalidade selecionada.

Essas informações são utilizadas no registro dos resultados e no cálculo das classificações.

### **3.9 Registro de resultados**

Os resultados são registrados conforme as regras de cada modalidade.

Na corrida, o sistema armazena os pontos das quatro rodadas.

No futebol, registra os placares dos tempos e, quando necessário, os pênaltis.

No basquete, registra as pontuações das equipes nas partidas.

### **3.10 Cálculo automático da pontuação**

O TeamUp realiza operações matemáticas para calcular os resultados e atualizar as classificações.

Na corrida, soma os pontos das rodadas.

No futebol, considera três pontos por vitória e um ponto por empate no tempo normal.

No basquete, considera dois pontos por vitória.

### **3.11 Classificação e ranking**

A classificação apresenta o desempenho dos participantes ou equipes conforme os resultados registrados.

O sistema compara as pontuações e organiza as informações para identificar os melhores colocados.

### **3.12 Hall da Fama**

O Hall da Fama é uma funcionalidade utilizada para registrar os campeões das competições.

O registro somente é permitido após a conclusão das rodadas ou partidas previstas e quando existe um vencedor definido.

Após o registro, a modalidade correspondente fica encerrada para alterações no campeonato, mantendo as consultas disponíveis.

### **3.13 Consultas e relatórios**

O sistema permite consultar as informações registradas, incluindo participantes, equipes, resultados e classificações.

Essas consultas auxiliam no acompanhamento dos campeonatos.

### **3.14 Encerramento do algoritmo**

O programa permanece em funcionamento por meio de menus e estruturas de repetição até que o usuário escolha a opção de saída.

Ao encerrar o VisualG, as informações registradas durante a execução não são preservadas permanentemente.

## **4. Considerações finais**

O desenvolvimento do TeamUp – Arena Gamer demonstra a aplicação dos conhecimentos de lógica de programação na criação de um sistema voltado ao gerenciamento de competições.

O projeto utiliza variáveis, vetores, estruturas condicionais, estruturas de repetição e operações matemáticas para organizar informações, registrar resultados e calcular classificações.

A implementação das três modalidades e do Hall da Fama contribuiu para ampliar as funcionalidades do programa e colocar em prática os conteúdos estudados no curso de Análise e Desenvolvimento de Sistemas.

## **5. Integrantes**

- Alan da Silva do Nascimento
- Alex Dias do Nascimento
- Danilo Rodrigues de Araújo
- Júlia de Oliveira dos Santos
- Kawan Wayner Bezerra da Silva
- Nicolas Pereira de Souza
