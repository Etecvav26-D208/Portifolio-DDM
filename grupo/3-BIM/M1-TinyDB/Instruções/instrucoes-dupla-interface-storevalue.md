# Instruções — Dupla B (Maria Eduarda & Mariana)
## Projeto: App de Lista de Tarefas com TinyDB — DDM

---

## 1. Resumo do projeto

Vamos construir, no **MIT App Inventor**, um aplicativo de lista de tarefas que **não perde os dados quando o app fecha**. Isso é feito usando o componente **TinyDB**, que funciona como um banco de dados local guardado no próprio celular.

O aplicativo precisa, no total (entre todas as etapas do grupo):

1. Permitir digitar uma nova tarefa
2. Adicionar a tarefa a uma lista
3. Mostrar todas as tarefas cadastradas
4. Salvar automaticamente no TinyDB
5. Recuperar as tarefas quando o app é reaberto
6. Selecionar uma tarefa da lista
7. Excluir a tarefa selecionada
8. Apagar todas as tarefas

Os blocos centrais que o professor quer ver bem compreendidos são: **`StoreValue`**, **`GetValue`** e **`ClearTag`**.

---

## 2. Divisão de etapas do grupo

O trabalho foi dividido em etapas sequenciais — cada uma depende da anterior estar pronta e testada:

| Etapa | O que é | Responsável |
|---|---|---|
| **1** | Interface (telas do app) | **Vocês** |
| **2** | Adicionar tarefa + salvar (`StoreValue`) | **Vocês** |
| 3 | Carregar tarefas salvas (`GetValue`) | Natan & Pietro |
| 4 | Selecionar e excluir uma tarefa | Natan & Pietro |
| 5 | Apagar tudo (`ClearTag`) | Natan & Pietro |

**Por que vocês começam?** Porque a interface e o armazenamento inicial são a base de tudo — sem eles prontos, ninguém mais consegue avançar. É a parte mais estrutural do projeto, e por isso também a que vamos revisar com mais atenção antes de seguir para as próximas etapas. Se algo sair torto aqui, o efeito se espalha pro resto do app — então capricho nessa parte importa muito.

---

## 3. Estrutura de telas (definido antes de começar)

Para o app parecer profissional — e não um formulário solto numa tela só — vamos usar **duas telas**:

- **Screen1 (tela principal):** mostra a lista de tarefas (`ListView`) e os botões `Nova Tarefa`, `Excluir selecionada` e `Apagar tudo`.
- **Screen2 (Nova Tarefa):** tem uma caixa de texto (`TextBox`) para digitar a tarefa e um botão `Salvar`, que grava a tarefa e volta para a Screen1.

Isso é importante: **o TinyDB é compartilhado automaticamente entre as duas telas**, então não precisa se preocupar em "passar dados" de uma tela pra outra manualmente — ele funciona como uma gaveta única acessível de qualquer tela do app.

> **Observação sobre a Screen2:** ao montar essa tela, evitem deixá-la "engessada" 
> só para adicionar tarefas novas (por exemplo, evitem textos ou lógicas fixas 
> como "esta tela sempre cria uma tarefa nova"). Se o grupo decidir implementar 
> a funcionalidade opcional de **editar tarefa** mais adiante, essa mesma tela 
> poderá ser reaproveitada para isso — desde que os componentes estejam 
> nomeados de forma neutra (ex: `TextBoxTarefa`, não `TextBoxNovaTarefa`).

---

## 4. O que vocês precisam fazer

### Etapa 1 — Interface

**O quê:** Montar as duas telas (Screen1 e Screen2) no Designer, com os componentes: `ListView`, três `Buttons` na Screen1, um `TextBox` e um `Button` na Screen2, e um componente `TinyDB` (pode ficar em qualquer uma das telas, ele funciona pro app inteiro).

**Por quê:** É a fundação visual e estrutural — sem ela, não existe onde a lógica das próximas etapas "morar".

**O que usar:** Componentes `Screen`, `ListView`, `Button`, `TextBox`, `TinyDB`, na paleta padrão do App Inventor (User Interface + Storage).

⚠️ **Atenção à aparência desde já.** Mesmo que o visual seja refinado depois (o Natan pretende revisar isso ao final), a base já deve nascer organizada e agradável: espaçamento entre elementos, textos legíveis, botões com nomes claros (`Nova Tarefa`, não `Button1`). Uma interface bagunçada desde o início gera retrabalho maior depois do que fazer com cuidado agora.

### Etapa 2 — Adicionar tarefa e salvar

**O quê:** Quando o botão `Salvar` da Screen2 for clicado, a tarefa digitada precisa ser **adicionada a uma lista** (isso é diferente de salvar um texto único — é uma lista de itens) e essa lista **gravada no TinyDB**. Depois, a tela deve voltar para a Screen1.

**Por quê:** Esse é o coração do armazenamento do app. Se a lista não for salva corretamente aqui, nada nas etapas seguintes (carregar, excluir) vai funcionar direito — porque elas dependem do formato exato de como os dados foram guardados.

**O que usar:** Bloco `TinyDB1.StoreValue`. Vocês vão precisar entender a diferença entre guardar **um valor** e guardar **uma lista de valores** — pesquisem sobre como o `StoreValue` lida com listas no App Inventor antes de montar o bloco. O bloco `close screen` (ou similar) é o que devolve o controle pra Screen1.

💡 **Dica de teste:** como a exibição da lista (`GetValue`) é etapa de outra dupla, vocês não vão ver visualmente se salvou certo ainda. Um jeito simples de conferir: usem um `Label` temporário na Screen2 pra mostrar o conteúdo salvo logo após o `StoreValue`, só para validar que está funcionando. Depois podem remover esse label de teste.

---

## 5. Sobre os commits

Mesmo trabalhando juntas fisicamente na mesma tela do computador, **cada uma de vocês deve commitar usando a própria conta do GitHub**, refletindo o que de fato cada uma fez ou decidiu. Isso é o que garante que o professor consiga ver a participação individual dentro do trabalho em grupo. Não faz sentido uma fazer todos os commits "pelas duas" — dividam entre si (por exemplo: uma commita a Screen1, a outra a Screen2, ou alternando por funcionalidade).

Façam commits **durante o processo**, não um único commit gigante no final.

---

## 6. Antes de considerar pronto

- [ ] As duas telas existem e têm todos os componentes nomeados claramente (sem espaços/acentos)
- [ ] É possível digitar uma tarefa na Screen2 e voltar pra Screen1 ao salvar
- [ ] A tarefa está sendo realmente adicionada à lista (não sobrescrevendo a anterior)
- [ ] O `StoreValue` está gravando a lista completa, não só o último item
- [ ] Testaram fechar e reabrir o app (mesmo sem visualização ainda, verifiquem via label de teste) para confirmar que o dado persiste
- [ ] Componentes e telas com aparência organizada, mesmo que simples
- [ ] Commits feitos por cada uma, com mensagens claras do que foi feito

Quando isso estiver validado, avisem o grupo — é o sinal pra Natan e Pietro seguirem com as etapas 3, 4 e 5 em cima do que vocês construíram.
