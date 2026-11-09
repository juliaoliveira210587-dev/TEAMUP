# TEAMUP
Sistema de gerenciamento de campeonatos de e-sports desenvolvido em VisualG, com cadastro de equipes, jogadores, partidas, resultados e classificação automática.
# TEAMUP — Sistema de Gestão de Campeonatos

## 1. Apresentação do projeto

O **TeamUp** é um projeto acadêmico de gerenciamento de campeonatos e competições, desenvolvido em Portugol utilizando o ambiente VisualG.

O sistema foi pensado para auxiliar na organização de campeonatos de e-sports em uma Arena Gamer. O algoritmo também permite configurar outras modalidades esportivas, como futebol, basquete, corrida e xadrez, além de uma opção personalizada.

O programa utiliza conceitos de lógica de programação para realizar cadastros, organizar partidas, registrar resultados, calcular classificações e apresentar relatórios.

No código-fonte, o algoritmo é identificado como `Sistema_Gestao_Campeonatos_Universal`, enquanto **TeamUp** é o nome do projeto.

## 2. Funcionamento geral do sistema

Ao iniciar o programa, o usuário escolhe a modalidade da competição. A partir dessa escolha, o algoritmo configura as regras de pontuação, a possibilidade de empate e as informações relacionadas aos locais das disputas.

Em seguida, o sistema apresenta duas áreas principais:

**Painel do Administrador:** permite cadastrar equipes, jogadores e locais, agendar partidas, registrar resultados, visualizar a classificação e consultar relatórios.

**Área do Jogador / Consulta Pública:** permite acompanhar a classificação geral, consultar participantes e visualizar as partidas agendadas ou finalizadas.

As informações são armazenadas em variáveis e vetores durante a execução do programa.

## 3. Explicação das principais partes do código

### 3.1 Identificação do algoritmo

```portugol
algoritmo "Sistema_Gestao_Campeonatos_Universal"
```

O comando `algoritmo` identifica o programa desenvolvido no VisualG.

O nome utilizado indica que o sistema foi estruturado para gerenciar diferentes modalidades de competição.

As linhas iniciadas por `//` representam comentários utilizados para organizar e documentar o código, sem interferir na execução.

### 3.2 Declaração de variáveis

```portugol
var
   nome_torneio: caractere
   nome_modalidade: caractere
   permite_empate: logico
   pts_vitoria: inteiro
   pts_empate: inteiro
   pts_derrota: inteiro
```

A seção `var` é utilizada para declarar as variáveis do algoritmo.

As variáveis do tipo `caractere` armazenam textos, como o nome do torneio. As do tipo `inteiro` armazenam números, como os pontos atribuídos às equipes. Já as do tipo `logico` armazenam valores VERDADEIRO ou FALSO.

Essas variáveis permitem definir e controlar as regras da competição.

### 3.3 Utilização de vetores

```portugol
eq_nome: vetor[1..8] de caractere
eq_pontos: vetor[1..8] de inteiro
jog_nome: vetor[1..32] de caractere
jog_equipe: vetor[1..32] de inteiro
```

Os vetores são utilizados para armazenar várias informações do mesmo tipo em posições diferentes.

Por exemplo, `eq_nome[1]` representa o nome da primeira equipe cadastrada, enquanto `eq_pontos[1]` armazena sua pontuação.

O vetor `jog_equipe` permite identificar a qual equipe cada jogador está vinculado.

Essa organização facilita o armazenamento e a consulta dos registros durante a execução do sistema.

### 3.4 Inicialização dos dados

```portugol
inicio
   tot_equipes <- 0
   tot_jogadores <- 0
   tot_partidas <- 0
```

O comando `inicio` indica onde começa a execução do algoritmo.

O operador `<-` atribui valores às variáveis.

Nesse trecho, os contadores são inicializados com zero porque ainda não existem equipes, jogadores ou partidas cadastrados.

### 3.5 Estruturas de repetição

```portugol
para i de 1 ate 20 faca
   part_realizada[i] <- FALSO
fimpara
```

O comando `para` executa repetidamente um conjunto de instruções.

Nesse caso, o algoritmo percorre as posições do vetor de partidas e define que todas estão inicialmente marcadas como não realizadas.

O comando `fimpara` encerra a repetição.

### 3.6 Configuração da modalidade

```portugol
se (opModalidade = 4) entao
   nome_torneio <- "Torneio de e-Sports"
   nome_modalidade <- "e-Sports (FPS / MOBA)"
   unidade_placar <- "Rounds/Mapas"
   desc_local <- "Servidor / Lobby"
   permite_empate <- FALSO
   pts_vitoria <- 3
   pts_empate <- 0
   pts_derrota <- 0
   infra_nome[1] <- "Servidor Alpha (BR)"
   infra_tipo[1] <- "Lobby Oficial"
   infra_nome[2] <- "Servidor Beta (BR)"
   infra_tipo[2] <- "Lobby Secundario"
fimse
```

O comando `se` verifica a modalidade selecionada pelo usuário.

Quando a opção 4 é escolhida, o sistema configura um torneio de e-sports, definindo o tipo de placar, os servidores utilizados e as regras de pontuação.

Nessa modalidade, não são permitidos empates, e cada vitória corresponde a três pontos.

O algoritmo também possui condições específicas para outras modalidades e permite uma configuração personalizada.

### 3.7 Menu principal

```portugol
repita
   limpatela
   escreval(" [1] Painel do Administrador (Cadastros e Sumulas)")
   escreval(" [2] Area do Jogador / Consulta Publica")
   escreval(" [0] Sair do Sistema")
   escreva("Opcao: ")
   leia(opcao_principal)
```

O menu principal apresenta as opções de navegação do sistema.

O comando `repita` inicia uma estrutura de repetição, enquanto `limpatela` limpa a tela antes de apresentar as informações.

Os comandos `escreva` e `escreval` exibem mensagens, e `leia` recebe a opção digitada pelo usuário.

O menu permanece em funcionamento até que o usuário selecione a opção de saída.

### 3.8 Cadastro de equipes

```portugol
tot_equipes <- tot_equipes + 1
leia(eq_nome[tot_equipes])
eq_jogos[tot_equipes] <- 0
eq_vitorias[tot_equipes] <- 0
eq_empates[tot_equipes] <- 0
eq_derrotas[tot_equipes] <- 0
eq_pontos[tot_equipes] <- 0
```

Ao cadastrar uma equipe, o algoritmo aumenta o contador `tot_equipes` em uma unidade.

Em seguida, recebe o nome da equipe e o armazena no vetor correspondente.

As estatísticas são inicializadas com zero, permitindo que cada equipe comece a competição sem partidas disputadas ou pontos acumulados.

### 3.9 Cadastro de jogadores

```portugol
tot_jogadores <- tot_jogadores + 1
leia(jog_nome[tot_jogadores])
leia(jog_posicao[tot_jogadores])
leia(jog_identificador[tot_jogadores])
```

O sistema recebe o nome, a função e a identificação do jogador.

Após o preenchimento, solicita o identificador da equipe à qual o participante será vinculado.

```portugol
se (idEq >= 1) e (idEq <= tot_equipes) entao
   jog_equipe[tot_jogadores] <- idEq
   escreval("Vinculado com sucesso!")
senao
   jog_equipe[tot_jogadores] <- 1
   escreval("ID invalido. Alocado no ID 1.")
fimse
```

A estrutura condicional verifica se o identificador informado corresponde a uma equipe cadastrada.

Quando o ID é válido, o jogador é associado à equipe selecionada. Caso contrário, o código o associa automaticamente à primeira equipe e apresenta uma mensagem informativa.

### 3.10 Cadastro de infraestrutura

```portugol
tot_infra <- tot_infra + 1
leia(infra_nome[tot_infra])
leia(infra_tipo[tot_infra])
infra_status[tot_infra] <- "Disponivel"
```

Essa funcionalidade permite registrar os locais utilizados nas competições, como arenas, pistas e servidores.

O algoritmo armazena o nome, o tipo e o status de cada local.

O status inicial é definido como disponível e pode ser atualizado durante o agendamento e a finalização das partidas.

### 3.11 Agendamento de partidas

```portugol
part_timeA[tot_partidas] <- tA
part_timeB[tot_partidas] <- tB
part_infra[tot_partidas] <- inf
part_realizada[tot_partidas] <- FALSO
infra_status[inf] <- "Ocupado"
```

O algoritmo registra os identificadores das duas equipes e do local selecionado para a disputa.

A partida recebe o valor FALSO na variável `part_realizada`, indicando que ainda não aconteceu.

O status do local utilizado também é atualizado para ocupado.

O código verifica se existem pelo menos dois participantes cadastrados antes de permitir o agendamento, mas não realiza todas as validações possíveis dos identificadores informados.

### 3.12 Registro de resultados

```portugol
se (nao permite_empate) e (gA = gB) entao
   escreval("Este modo nao permite empates!")
senao
   part_golsA[idP] <- gA
   part_golsB[idP] <- gB
   part_realizada[idP] <- VERDADEIRO
   infra_status[part_infra[idP]] <- "Disponivel"
```

Esse bloco verifica se o resultado informado respeita as regras da modalidade.

Quando o empate não é permitido e as duas equipes apresentam o mesmo resultado, o sistema exibe uma mensagem e não finaliza a partida.

Caso o resultado seja válido, o algoritmo armazena o placar, identifica a partida como realizada e altera o status do local para disponível.

### 3.13 Cálculo automático da pontuação

```portugol
se (gA > gB) entao
   eq_vitorias[tA] <- eq_vitorias[tA] + 1
   eq_derrotas[tB] <- eq_derrotas[tB] + 1
   eq_pontos[tA] <- eq_pontos[tA] + pts_vitoria
   eq_pontos[tB] <- eq_pontos[tB] + pts_derrota
```

O algoritmo compara os resultados das equipes para identificar a vencedora.

Quando a equipe A possui um resultado maior que a equipe B, o sistema registra uma vitória para A, uma derrota para B e atualiza a pontuação das duas equipes.

O código também possui condições para registrar vitória da equipe B e empates, quando permitidos pela modalidade.

Dessa forma, as estatísticas e a pontuação são atualizadas automaticamente após o lançamento de um resultado válido.

### 3.14 Classificação e ranking

```portugol
se (eq_pontos[idB] > eq_pontos[idA]) entao
   trocar <- VERDADEIRO
fimse
```

Esse trecho compara a pontuação de duas equipes.

Quando a segunda equipe possui mais pontos que a primeira, a variável `trocar` recebe VERDADEIRO, indicando que suas posições devem ser invertidas.

```portugol
se (trocar) entao
   aux <- rank[i]
   rank[i] <- rank[j]
   rank[j] <- aux
fimse
```

A variável `aux` armazena temporariamente uma posição, permitindo a troca dos identificadores no vetor `rank`.

O algoritmo utiliza estruturas de repetição para comparar os participantes e organizar a classificação.

**Critérios de desempate:**

Nas modalidades que não são corrida, o código considera:

1. Maior pontuação;
2. Maior saldo de pontos, gols ou rounds;
3. Maior quantidade de pontos, gols ou rounds a favor.

Na modalidade corrida, são considerados a pontuação, a quantidade de vitórias e os pódios.

Assim, a classificação é organizada conforme as regras implementadas no algoritmo.

### 3.15 Relatório de participantes

```portugol
para j de 1 ate tot_jogadores faca
   se (jog_equipe[j] = i) entao
      escreval("   - [", jog_identificador[j], "] ", jog_nome[j], " (Funcao: ", jog_posicao[j], ")")
   fimse
fimpara
```

O algoritmo percorre os jogadores cadastrados e verifica quais estão vinculados à equipe consultada.

Quando encontra um participante pertencente à equipe, apresenta sua identificação, nome e função.

Isso permite organizar e visualizar os integrantes de cada equipe.

### 3.16 Relatório de infraestrutura

```portugol
para i de 1 ate tot_infra faca
   escreval("Pista/Local [", i, "]: ", infra_nome[i])
   escreval("  Tipo   : ", infra_tipo[i])
   escreval("  Status : ", infra_status[i])
fimpara
```

O sistema percorre os locais e servidores cadastrados, apresentando suas informações.

O relatório mostra o nome, o tipo e o status registrado para cada recurso.

Essa funcionalidade permite acompanhar os locais utilizados nas competições, sem representar um inventário completo dos equipamentos de rede.

### 3.17 Área do jogador e consulta pública

```portugol
escreval(" [1] Ver Classificacao Geral")
escreval(" [2] Consultar Participantes e Equipes")
escreval(" [3] Calendario de Disputas")
escreval(" [0] Voltar ao Menu Principal")
```

A área de consulta pública permite acompanhar as informações da competição sem acessar as funcionalidades administrativas.

O usuário pode visualizar a classificação geral, consultar as equipes e seus participantes e acompanhar as disputas registradas.

O calendário apresenta as partidas como agendadas ou finalizadas, incluindo os resultados das partidas concluídas.

### 3.18 Encerramento do algoritmo

```portugol
ate (opcao_principal = 0)

limpatela
escreval("Sistema finalizado com sucesso. Ate logo!")
fimalgoritmo
```

O comando `ate` determina a condição de encerramento do menu principal.

Quando o usuário seleciona a opção zero, o sistema encerra a repetição, apresenta uma mensagem de despedida e finaliza a execução com o comando `fimalgoritmo`.

## 4. Considerações finais

O desenvolvimento do TeamUp demonstra a aplicação de conceitos de lógica de programação na criação de um sistema de gerenciamento de competições.

O algoritmo utiliza variáveis, vetores, estruturas condicionais, estruturas de repetição e operações matemáticas para organizar dados, registrar resultados e apresentar classificações.

A integração dessas funcionalidades permite compreender como a lógica de programação pode ser utilizada para solucionar problemas relacionados à organização de campeonatos.

## 5. Integrantes

- Alan da Silva do Nascimento
- Alex Dias do Nascimento
- Danilo Rodrigues de Araujo
- Julia de Oliveira dos Santos
- Kawan Wayner Bezerra da Silva
- Nicolas Pereira de Souza
