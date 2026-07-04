
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
# 3. Funcionamento do TinyDB

O TinyDB utiliza um modelo de armazenamento baseado em **Tags (chaves)** e **Values (valores)**. Cada informação é salva utilizando uma Tag, que funciona como um identificador único, e um Value, que corresponde ao dado armazenado. Esse modelo, conhecido como **chave-valor (key-value)**, permite localizar rapidamente qualquer informação gravada no dispositivo (MIT APP INVENTOR, 2026).

Por exemplo, um aplicativo pode utilizar a Tag **"Nome"** para armazenar o valor **"Maria"**. Quando o aplicativo precisar exibir o nome do usuário, basta buscar o valor associado à Tag correspondente.

## Tags (Chaves)

As **Tags** são utilizadas para identificar cada informação armazenada no TinyDB. Cada Tag deve possuir um nome único e representativo, facilitando a organização e a recuperação dos dados.

### Exemplos de Tags

| Tag | Informação armazenada |
|------|-----------------------|
| Nome | Maria |
| Idade | 20 |
| Cidade | Jundiaí |
| Pontuação | 850 |
| Tema | Escuro |

É recomendado utilizar nomes simples e objetivos para evitar erros durante o desenvolvimento.

---

## Values (Valores)

Os **Values** representam os dados associados às Tags. O TinyDB permite armazenar diferentes tipos de informações, como:

- Textos;
- Números;
- Valores lógicos (verdadeiro ou falso);
- Listas;
- Datas;
- Configurações do aplicativo.

Essa flexibilidade permite desenvolver diferentes tipos de aplicativos utilizando um único componente de armazenamento.

---

## Gravação de informações

Para armazenar um dado no TinyDB utiliza-se o bloco **StoreValue**. Esse bloco recebe uma Tag e um Value, gravando a informação na memória interna do dispositivo.

Sempre que um novo valor é salvo utilizando uma Tag já existente, o valor anterior é substituído automaticamente (MIT APP INVENTOR, 2026).

### Exemplo

```text
Tag: Nome
Valor: Maria
```

Após executar o bloco, a informação ficará armazenada permanentemente.

---

## Leitura de informações

Para recuperar um dado utiliza-se o bloco **GetValue**. Basta informar a Tag correspondente e o TinyDB retornará o valor armazenado.

Caso a Tag não exista, é possível definir um valor padrão (*Default Value*), evitando erros na aplicação.

### Exemplo

```text
Tag pesquisada: Nome

Resultado:
Maria
```

---

## Atualização de dados

A atualização ocorre quando um novo valor é gravado utilizando a mesma Tag.

### Exemplo

Antes:

```text
Nome → Maria
```

Depois:

```text
Nome → Ana
```

O valor "Maria" será substituído automaticamente por "Ana".

---

## Remoção de dados

Quando uma informação não é mais necessária, ela pode ser removida utilizando os blocos **ClearTag** ou **ClearAll**.

A remoção de dados ajuda a manter o armazenamento organizado e evita o acúmulo de informações desnecessárias.

---

## Figura 3 – Funcionamento do TinyDB

```text
Aplicativo
     │
     ▼
StoreValue
     │
     ▼
 Tag: Nome
 Valor: Maria
     │
     ▼
 TinyDB
     │
     ▼
Memória do dispositivo
```

---

# 4. Componentes Relacionados

O TinyDB possui quatro blocos principais responsáveis pelo gerenciamento das informações armazenadas.

## StoreValue

O bloco **StoreValue** grava informações no TinyDB.

Ele recebe dois parâmetros:

- Tag;
- Value.

Sempre que utilizado, o valor ficará armazenado até ser alterado ou removido.

### Quando utilizar?

- Salvar configurações;
- Cadastrar usuários;
- Armazenar listas;
- Salvar pontuações de jogos;
- Registrar preferências do usuário.

---

## GetValue

O bloco **GetValue** recupera um valor armazenado anteriormente.

Caso a Tag não exista, pode retornar um valor padrão definido pelo desenvolvedor.

### Quando utilizar?

- Exibir dados do usuário;
- Recuperar configurações;
- Carregar listas;
- Mostrar pontuações salvas.

---

## ClearTag

O bloco **ClearTag** remove apenas uma informação específica.

### Exemplo

Antes:

```text
Nome → Maria
Cidade → Jundiaí
```

Após executar **ClearTag("Cidade")**:

```text
Nome → Maria
```

Somente a Tag "Cidade" será removida.

### Quando utilizar?

- Excluir cadastros;
- Apagar configurações específicas;
- Remover informações antigas.

---

## ClearAll

O bloco **ClearAll** remove todas as informações armazenadas no TinyDB.

Após sua execução, todas as Tags e seus respectivos valores são apagados.

### Quando utilizar?

- Restaurar configurações de fábrica;
- Limpar completamente os dados do aplicativo;
- Reiniciar o armazenamento local.

---

## Tabela comparativa dos blocos

| Bloco | Função | Quando utilizar |
|--------|---------|----------------|
| StoreValue | Armazena informações | Salvar dados |
| GetValue | Recupera informações | Ler dados salvos |
| ClearTag | Remove uma Tag | Excluir um dado específico |
| ClearAll | Remove todos os dados | Limpar completamente o TinyDB |

Segundo a documentação oficial do MIT App Inventor (2026), esses quatro blocos representam as principais operações realizadas no TinyDB e permitem implementar aplicações capazes de armazenar informações de forma simples e eficiente.

# 5. Aplicações Práticas do TinyDB

O TinyDB é amplamente utilizado em aplicativos que precisam armazenar pequenas quantidades de dados diretamente no dispositivo do usuário. Como os dados permanecem salvos mesmo após o aplicativo ser fechado, ele é ideal para aplicações que não dependem de internet (MIT APP INVENTOR, 2026).

## Exemplos de utilização

### Lista de tarefas

O TinyDB pode armazenar tarefas criadas pelo usuário, permitindo que elas permaneçam salvas mesmo após o aplicativo ser fechado.

### Cadastro de usuários

Informações como nome, telefone e e-mail podem ser armazenadas localmente para facilitar o uso do aplicativo.

### Controle financeiro

Aplicativos de finanças podem salvar despesas, receitas e saldo diretamente no dispositivo.

### Jogos

É possível armazenar:

- Pontuação;
- Recordes;
- Nível alcançado;
- Configurações do jogador.

### Configurações do aplicativo

O TinyDB permite salvar preferências do usuário, como:

- Tema claro ou escuro;
- Idioma;
- Volume;
- Tamanho da fonte.

---

## Figura 4 – Exemplos de utilização

```text
TinyDB
│
├── Lista de tarefas
├── Cadastro
├── Jogos
├── Controle financeiro
└── Configurações
```

---

# 6. Diferença entre TinyDB e TinyWebDB

Embora possuam nomes semelhantes, TinyDB e TinyWebDB apresentam diferenças importantes.

O TinyDB armazena informações na memória do próprio dispositivo. Já o TinyWebDB utiliza um servidor na Internet para armazenar os dados, permitindo que diferentes dispositivos compartilhem as mesmas informações (MIT APP INVENTOR, 2026).

## Comparação

| Característica | TinyDB | TinyWebDB |
|----------------|---------|-----------|
| Local de armazenamento | Dispositivo | Servidor |
| Necessita Internet | Não | Sim |
| Compartilha dados | Não | Sim |
| Velocidade | Alta | Depende da conexão |
| Indicado para | Aplicativos simples | Aplicativos colaborativos |

## Quando utilizar?

### TinyDB

- Aplicativos offline;
- Jogos;
- Agenda;
- Lista de tarefas;
- Configurações.

### TinyWebDB

- Chat;
- Aplicativos escolares;
- Sistemas online;
- Compartilhamento entre usuários.

---

# 7. Boas Práticas

Durante o desenvolvimento de aplicativos utilizando o TinyDB, algumas recomendações ajudam a manter os dados organizados e evitar problemas.

## Utilizar Tags organizadas

As Tags devem possuir nomes simples e fáceis de identificar.

Exemplos:

- Nome
- Email
- Senha
- Pontuação
- Configurações

---

## Evitar informações desnecessárias

Armazenar apenas os dados realmente necessários melhora o desempenho do aplicativo.

---

## Proteger informações sensíveis

O TinyDB não criptografa automaticamente os dados. Portanto, informações como senhas e dados bancários não devem ser armazenadas diretamente nesse componente. Para esses casos, recomenda-se utilizar mecanismos de criptografia ou serviços especializados em armazenamento seguro (OWASP FOUNDATION, 2021).

---

## Limpar informações antigas

Utilizar os blocos **ClearTag** e **ClearAll** quando necessário evita o acúmulo de dados desnecessários.

---

## Testar o aplicativo

Antes da publicação, é importante verificar se todas as informações estão sendo gravadas, recuperadas e removidas corretamente.

---

## Figura 5 – Boas práticas

```text
Boas práticas
│
├── Organizar Tags
├── Salvar apenas dados necessários
├── Não armazenar senhas
├── Testar o aplicativo
└── Limpar dados antigos
```

# 8. Conclusão

O TinyDB é um dos componentes mais importantes do MIT App Inventor para o armazenamento local de informações. Sua utilização permite desenvolver aplicativos capazes de manter dados salvos mesmo após o encerramento da aplicação, proporcionando maior praticidade ao usuário.

Durante esta pesquisa foi possível compreender o funcionamento do TinyDB, seus principais blocos de programação, aplicações práticas e diferenças em relação ao TinyWebDB. Também foram apresentadas boas práticas para organizar e proteger os dados armazenados.

Embora seja uma excelente solução para aplicativos simples e que funcionam sem acesso à Internet, o TinyDB possui limitações relacionadas ao compartilhamento de informações entre diferentes dispositivos. Para aplicações colaborativas ou que necessitam de sincronização online, recomenda-se utilizar bancos de dados remotos.

Conclui-se que o TinyDB é uma ferramenta simples, eficiente e muito importante para o desenvolvimento de aplicativos móveis no MIT App Inventor, principalmente em projetos educacionais e de pequeno porte (MIT APP INVENTOR, 2026).

---

# Referências

MIT APP INVENTOR. **MIT App Inventor Documentation.** Disponível em: <https://appinventor.mit.edu/>. Acesso em: 03 jul. 2026.

MIT APP INVENTOR. **TinyDB Component Documentation.** Disponível em: <https://ai2.appinventor.mit.edu/reference/components/storage.html>. Acesso em: 03 jul. 2026.

OWASP FOUNDATION. **OWASP Top 10: The Ten Most Critical Web Application Security Risks 2021.** Disponível em: <https://owasp.org/www-project-top-ten/>. Acesso em: 03 jul. 2026.

WOLBER, David; ABELSON, Hal; FRIEDMAN, Mark; GRISWOLD, Ellen. **App Inventor 2: Create Your Own Android Apps.** Sebastopol: O'Reilly Media, 2015.

---

# Sugestões de imagens

Para enriquecer o trabalho, você pode inserir as seguintes imagens:

- Tela inicial do MIT App Inventor.
- Componente TinyDB no Designer.
- Bloco **StoreValue**.
- Bloco **GetValue**.
- Bloco **ClearTag**.
- Bloco **ClearAll**.
- Fluxograma de funcionamento do TinyDB.

Essas imagens podem ser capturadas do próprio MIT App Inventor ou obtidas na documentação oficial, citando a fonte.
