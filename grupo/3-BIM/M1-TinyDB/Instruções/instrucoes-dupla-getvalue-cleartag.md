# Instruções — Dupla A (Natan & Pietro)
## Projeto: App de Lista de Tarefas com TinyDB — DDM

---

## 1. Resumo do projeto

App de lista de tarefas no **MIT App Inventor**, com persistência local via **TinyDB** — as tarefas continuam salvas mesmo depois do app fechado e reaberto.

Funcionalidades obrigatórias do professor:

1. Digitar uma nova tarefa
2. Adicionar a tarefa a uma lista
3. Mostrar todas as tarefas cadastradas
4. Salvar automaticamente no TinyDB
5. Recuperar as tarefas quando o app é reaberto
6. Selecionar uma tarefa da lista
7. Excluir a tarefa selecionada
8. Apagar todas as tarefas

Blocos centrais exigidos: **`StoreValue`**, **`GetValue`**, **`ClearTag`**.

---

## 2. Divisão de etapas do grupo

| Etapa | O que é | Responsável |
|---|---|---|
| 1 | Interface (Screen1 + Screen2) | Maria Eduarda & Mariana |
| 2 | Adicionar tarefa + salvar (`StoreValue`) | Maria Eduarda & Mariana |
| **3** | Carregar tarefas salvas (`GetValue`) | **Vocês** |
| **4** | Selecionar e excluir uma tarefa | **Vocês** |
| **5** | Apagar tudo (`ClearTag`) | **Vocês** |

Vocês entram depois que a interface e o armazenamento inicial estiverem prontos e testados pela outra dupla. Isso significa que, antes de tudo, o primeiro passo de vocês é **revisar o que foi entregue** — não assumir que está perfeito, e sim confirmar que a lista está sendo salva do jeito esperado antes de construir em cima.

---

## 3. Estrutura de telas (já definida)

- **Screen1 (principal):** `ListView` com as tarefas + botões `Nova Tarefa`, `Excluir selecionada`, `Apagar tudo`
- **Screen2 (Nova Tarefa):** `TextBox` + botão `Salvar`, grava no TinyDB e retorna pra Screen1

O `TinyDB` é compartilhado entre as duas telas automaticamente. Isso importa pra vocês porque a Etapa 3 (`GetValue`) vai rodar dentro do evento **`Screen1.Initialize`** — e esse evento dispara não só quando o app abre pela primeira vez, mas também **toda vez que a Screen2 fecha e volta pra Screen1**. É esse comportamento que vai fazer a lista aparecer atualizada depois de adicionar uma tarefa nova.

---

## 4. O que vocês precisam fazer

### Etapa 3 — Carregar tarefas salvas

**O quê:** No evento `Screen1.Initialize`, buscar a lista de tarefas salva no TinyDB e usá-la para popular a `ListView`.

**Por quê:** É esse bloco que faz os dados "sobreviverem" ao fechamento do app — sem ele, tudo que a Dupla B salvou fica invisível pra sempre. É literalmente o requisito central da atividade: dados que persistem.

**O que usar:** Bloco `TinyDB1.GetValue`, com um **valor padrão** definido (pensem no que faz sentido retornar caso ainda não exista nenhuma tarefa salva — isso evita erro na primeira vez que o app roda). O resultado precisa ser conectado à propriedade `Elements` da `ListView`.

⚠️ **Ponto de atenção real:** o formato salvo pela Dupla B no `StoreValue` precisa bater exatamente com o que o `GetValue` espera receber de volta. Se a lista foi salva de um jeito e vocês tentam ler de outro, o app não quebra visivelmente — só mostra vazio ou dá erro silencioso. Testem isso com atenção antes de seguir pra próxima etapa.

### Etapa 4 — Selecionar e excluir uma tarefa

**O quê:** Capturar qual item foi selecionado na `ListView`, removê-lo da lista (por posição/índice, não por texto — evita bug se houver tarefas com nomes repetidos), atualizar a `ListView` visualmente e salvar a lista atualizada de volta no TinyDB.

**Por quê:** É a funcionalidade que dá controle real ao usuário sobre a lista — sem isso, o app só acumula tarefas pra sempre.

**O que usar:** Propriedade `ListView1.Selection` (ou `SelectionIndex`, dependendo de como preferirem trabalhar), bloco de lista `remove list item` (por índice), e de novo `TinyDB1.StoreValue` pra persistir a mudança.

💭 **Reflexão útil antes de montar:** pensem no que acontece se o usuário clicar em "excluir" sem ter selecionado nada antes — vale tratar esse caso pra não gerar erro.

### Etapa 5 — Apagar tudo

**O quê:** Ao clicar no botão `Apagar tudo`, limpar tanto a lista exibida na `ListView` quanto o dado salvo no TinyDB.

**Por quê:** É o bloco mais simples dos três centrais, mas o professor pede especificamente pra ver ele em uso — é o que garante que "apagar tudo" realmente zera o armazenamento, não só a exibição.

**O que usar:** `TinyDB1.ClearTag` (repara que é diferente de `ClearAll` — pesquisem a diferença entre os dois antes de escolher) e limpar a `ListView` visualmente também, já que apagar o dado salvo não atualiza sozinho o que está na tela.

💡 **Sugestão de UX:** pode valer a pena um `Notifier` de confirmação antes de apagar tudo, já que é uma ação irreversível — isso inclusive já contempla uma das funcionalidades opcionais do professor, se decidirem incluir.

---

## 5. Sobre os commits

Mesma regra da outra dupla: mesmo trabalhando juntos, **cada um commita com a própria conta**, refletindo o que de fato fez. Dividam por etapa ou por funcionalidade — o importante é que dê pra ver a contribuição individual de cada um no histórico.

---

## 6. Antes de considerar pronto

- [ ] Revisaram o trabalho da Dupla B antes de começar (interface + `StoreValue` funcionando)
- [ ] `GetValue` carrega a lista corretamente ao abrir o app pela primeira vez
- [ ] Lista também atualiza ao voltar da Screen2 pra Screen1 (sem precisar fechar o app inteiro)
- [ ] Selecionar e excluir uma tarefa funciona sem afetar as outras
- [ ] Tentativa de excluir sem seleção não quebra o app
- [ ] `Apagar tudo` limpa tela **e** TinyDB (testem fechando e reabrindo o app depois de apagar tudo)
- [ ] Testaram o fluxo completo do zero: abrir app vazio → adicionar → fechar → reabrir → ver que persistiu → excluir → apagar tudo
- [ ] Commits feitos por cada um, com mensagens claras

Quando isso estiver validado, o grupo entra na fase de revisão conjunta — todo mundo testando o app junto, garantindo que todos entendem os três blocos centrais, como o professor pede.
