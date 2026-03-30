# Instituição
Etec Vasco Antônio Venchiarutti

# Curso
Informática para Internet

# Turma
 2º Ano de Informática para Internet (2D)

# Autores
- Maria Eduarda Pinto de Oliveira Rodrigues
- Mariana Rasmussen Rezende Alves
- Natan Alexandro
- Pietro Fiorese Dopp

---
# Projeto

## My Days

## Descrição

### Objetivo do aplicativo

O aplicativo **MyDays** tem como objetivo permitir que o usuário registre como foi o seu dia de forma detalhada, incluindo humor, produtividade, atividades realizadas e reflexões pessoais personalizadas.

A proposta é funcionar como um diário digital interativo, ajudando o usuário a acompanhar sua rotina, sentimentos e evolução ao longo do tempo. E também com a praticidade de ter essas funções na palma da mão. 

---

### Funcionamento do aplicativo

O funcionamento do aplicativo ocorre em etapas obrigatórias:

#### Tela inicial
![Design 1 do App](/grupo/recursos-do-app/fotos_telas/Tela1.jpg)
Ao entrar no aplicativo, o usuário se depara com a tela “Hoje”, onde é solicitado que ele tire uma foto, ou selecione uma imagem da galeria do seu dia ou que o represente.

Essa etapa é obrigatória, ou seja, só é possível prosseguir após inserir a foto. 
O app verifica se a imagem padrão da tela foi alterada ao apertar o botão "Prosseguir", caso não tenha sido exibe um aviso.

---

#### Preenchimento das informações

Após clicar em “Prosseguir”, o usuário é direcionado para uma nova tela onde deve preencher todas as informações do dia.
![Design 1 do App](/grupo/recursos-do-app/fotos_telas/Tela2.jpg)

Os campos incluem:

- Humor do dia
  - Triste
  - Normal
  - Feliz

- Produtividade:
  - Nada Produtivo
  - Fiz algumas coisas
  - Bem produtivo

- Atividades realizadas:
  - Estudei
  - Saí de casa
  - Treinei
  - Interagi

 
- Ponto alto do dia (campo de texto)

- Ponto baixo do dia (opcinal)

- Relato do dia (campo de texto)

Todos os campos principais são obrigatórios para garantir um registro completo.

---

#### Finalização

Após preencher todas as informações, o usuário finaliza o registro do dia.
Aqui é onde entra a ação principal do TinyDB, ferramenta de banco de dados disponível no App Inventor. Aqui uma variável guarda todas as informações preencidas pelo usuário numa lista, e adicina também data dia da semana no momento exato do registro.
Assim o usuário termina direcionado para a tela "Hoje" novamente. 
OBS: é possóvel criar quantos registros quiser no dia, mas o processo da foto e preenchimento do formulário terão que ser repetidos.
![Design 1 do App](/grupo/recursos-do-app/fotos_telas/Tela3.jpg)
![Design 1 do App](/grupo/recursos-do-app/fotos_telas/Tela4.jpg)



---

#### Tela de histórico (Meu Diário)

Ao finalizar, o usuário pode clicar em "Meu Diário" é automaticamente direcionado para a tela “Meu Diário”, onde ficam armazenados todos os registros feitos.
![Design 1 do App](/grupo/recursos-do-app/fotos_telas/Tela5.jpg)


Cada registro apresenta:

- Data
- Dia da semana (ex: Sábado ou domingo)
- Resumo do dia

---

#### Visualização detalhada

Ao clicar em um registro, o usuário pode visualizar todas as informações salvas:

![Design 1 do App](/grupo/recursos-do-app/fotos_telas/Tela6.jpg)

- Foto do dia
- Humor
- Produtividade
- Atividades que selecionou
- Ponto alto
- Ponto baixo
- Texto do diário

Também existe a opção de excluir o registro e a opção de voltar, que fecha a tela.

---

### Conceitos utilizados da apostila

O projeto utilizou diversos conceitos do App Inventor, como:

- **Modo Design (Interface gráfica)**  
  Criação das telas com componentes visuais como Caixas de organização e uso de uma paleta de cores agradável (melhorado na versão atual do app). 

- **Modo Blocos (Programação)**  
  Desenvolvimento da lógica do aplicativo com funções de:
  - Imagens
  - Listas
  - Banco de Dados
  - Registros do usuário em caixas de texto
  - Notificador
  - Temporizador
  - Criação de variaveis e compartilhamento dessas entre as telas.

- **Eventos**  
  Ações baseadas na interação do usuário (cliques, seleção, etc.).

- **Uso de câmera**  
  Captura de imagem obrigatória no início.

- **Entrada e saída de dados**  
  Uso de TextBox, Labels e CheckBox que mudam de acordo com as informações do usuário.

- **Lógica condicional**  
  Validação dos campos obrigatórios através do uso de "processos".

- **Armazenamento de dados**  
  Salvamento dos registros para exibição no histórico.

---

### Recursos e componentes utilizados

- Camera e Image Picker → captura da foto  
- Button → ações (Prosseguir, Finalizar, Excluir)  
- Label → exibição de textos  
- TextBox → entrada de dados  
- CheckBox → seleção de atividades  
- Arranjos (Layouts) → organização da interface
- Notificador → avisos na tela
- Temporizador → na tela de suposto carregamento e salvamento de data
- TinyDB (ou similar) → armazenamento dos dados  

---

### Melhorias e ideias próprias

O aplicativo apresenta melhorias em relação aos exemplos da apostila:

- Uso de foto obrigatória
- Sistema completo de diário
- Histórico de registros
- Interface simples e intuitiva
- Navegação entre várias telas
- Uso de diferentes tipos de dados (imagem, texto e seleção)

---

# Print das telas do Design

(Insira aqui os prints das telas do aplicativo)

---

# Print das telas dos Blocos

(Insira aqui os prints da programação em blocos)

---

# Considerações finais

O desenvolvimento do aplicativo **MyDays** permitiu aplicar na prática diversos conceitos do App Inventor, indo muito além dos exemplos básicos.

O projeto se mostrou funcional e próximo de um aplicativo real, utilizando múltiplas telas, validação de dados, uso de câmera e armazenamento de informações.

Além disso, contribuiu para o desenvolvimento de habilidades como:

- raciocínio lógico  
- organização de ideias  
- criatividade  
- desenvolvimento de soluções digitais
- Possibilidade de tornar real uma ideia de app pessoal
