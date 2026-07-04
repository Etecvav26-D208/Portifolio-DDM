
# Pesquisa – App Inventor: Manipulação de Banco de Dados no Dispositivo (TinyDB)

## Integrantes

- Maria Eduarda Pinto de Oliveira Rodrigues 
- Mariana Rasmussen Rezende Alves 

---

# Introdução

Com o crescimento do uso de smartphones, os aplicativos móveis passaram a fazer parte do dia a dia das pessoas, sendo utilizados para estudos, trabalho, comunicação, entretenimento e organização pessoal. Muitos desses aplicativos precisam armazenar informações, como cadastros, configurações e listas, permitindo que os dados permaneçam disponíveis mesmo após o aplicativo ser fechado.

O **MIT App Inventor** é uma plataforma gratuita desenvolvida pelo Massachusetts Institute of Technology (MIT) que facilita a criação de aplicativos por meio da programação em blocos. Entre seus diversos componentes destaca-se o **TinyDB**, responsável pelo armazenamento local de informações no dispositivo móvel, sem necessidade de conexão com a Internet (MIT APP INVENTOR, 2026).

O objetivo desta pesquisa é apresentar o funcionamento do TinyDB, explicar seus principais recursos, demonstrar aplicações práticas, comparar o TinyDB com o TinyWebDB e destacar boas práticas para o armazenamento de dados em aplicativos desenvolvidos no MIT App Inventor.

---

# 1. O que é o MIT App Inventor?

O **MIT App Inventor** é uma plataforma gratuita e online utilizada para desenvolver aplicativos para dispositivos móveis Android e iOS utilizando programação em blocos. Ela foi criada para facilitar o aprendizado de programação, permitindo que estudantes e iniciantes desenvolvam aplicativos sem a necessidade de escrever códigos complexos (MIT APP INVENTOR, 2026).

O ambiente de desenvolvimento possui duas áreas principais:

- **Designer:** utilizado para criar a interface gráfica do aplicativo.
- **Blocks:** utilizado para programar o funcionamento do aplicativo através de blocos.

Essa forma de programação torna o desenvolvimento mais intuitivo e reduz a complexidade encontrada nas linguagens tradicionais.

### Para que ele é utilizado?

O App Inventor pode ser utilizado para desenvolver diversos tipos de aplicativos, como:

- Calculadoras;
- Jogos;
- Agenda de contatos;
- Lista de tarefas;
- Controle financeiro;
- Aplicativos educacionais;
- Sistemas de cadastro;
- Aplicativos de saúde.

Além do uso educacional, também pode ser utilizado em pequenos projetos pessoais e comerciais.

### Principais vantagens

Entre as principais vantagens destacam-se:

- Programação em blocos;
- Interface simples e intuitiva;
- Gratuito;
- Testes em tempo real no smartphone;
- Grande quantidade de componentes disponíveis;
- Ideal para iniciantes.

Segundo Wolber et al. (2015), o App Inventor possibilita que estudantes aprendam programação desenvolvendo aplicativos reais de maneira simples e interativa.

---

# 2. O que é o TinyDB?

O **TinyDB** é um componente não visível do MIT App Inventor responsável pelo armazenamento permanente de informações diretamente na memória do dispositivo móvel. Seu funcionamento baseia-se em pares de **Tag (chave)** e **Value (valor)**, permitindo gravar e recuperar dados facilmente (MIT APP INVENTOR, 2026).

### Qual é sua finalidade?

Sua principal finalidade é armazenar informações para que permaneçam disponíveis mesmo após o fechamento do aplicativo ou o desligamento do dispositivo.

O TinyDB pode armazenar diferentes tipos de dados, como:

- Textos;
- Números;
- Valores lógicos (verdadeiro ou falso);
- Listas;
- Configurações do aplicativo;
- Pontuações de jogos;
- Informações de usuários.

### Onde os dados são armazenados?

As informações ficam armazenadas na memória interna do próprio dispositivo onde o aplicativo está instalado. Esses dados permanecem disponíveis até que:

- O aplicativo seja desinstalado;
- O usuário apague os dados do aplicativo;
- O próprio aplicativo remova as informações utilizando os blocos do TinyDB.

### Vantagens do TinyDB

O TinyDB apresenta diversas vantagens:

- Não necessita de conexão com a Internet;
- Fácil implementação;
- Armazenamento permanente;
- Boa velocidade de acesso;
- Ideal para aplicativos simples;
- Integração fácil com outros componentes do App Inventor.

### Limitações do TinyDB

Apesar de suas vantagens, o TinyDB possui algumas limitações:

- Os dados ficam disponíveis apenas no dispositivo onde foram gravados;
- Não permite compartilhamento entre diferentes usuários;
- Não realiza sincronização online;
- Não é indicado para grandes volumes de dados.

Por isso, quando uma aplicação necessita compartilhar informações entre vários usuários ou dispositivos, recomenda-se utilizar componentes como o TinyWebDB ou bancos de dados hospedados em servidores.

---

## Figura 1 – Estrutura básica do MIT App Inventor

```text
MIT App Inventor
│
├── Designer
│     └── Criação da interface
│
└── Blocks
      └── Programação em blocos
```

---

## Figura 2 – Funcionamento do TinyDB

```text
Aplicativo
     │
     ▼
   TinyDB
     │
 ┌── Tag ─────────► Valor
 │
 ├── "Nome" ─────► "Maria"
 ├── "Idade" ────► 20
 └── "Cidade" ───► "Jundiaí"
```
