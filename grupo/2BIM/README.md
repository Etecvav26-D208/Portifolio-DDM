# Pesquisa – Segurança em Aplicações Web com PHP

## Integrantes

- Maria Eduarda Pinto de Oliveira Rodrigues
- Mariana Rasmussen Rezende Alves 
---

# Introdução

O desenvolvimento de aplicações web tornou-se essencial para empresas, instituições de ensino, bancos, redes sociais e diversos outros serviços que fazem parte do cotidiano das pessoas. Com o crescimento da utilização da Internet, aumentou também a quantidade de informações pessoais armazenadas nesses sistemas, como nomes, documentos, endereços, dados bancários e senhas. Dessa forma, garantir a segurança dessas informações passou a ser uma das maiores responsabilidades dos desenvolvedores.

A segurança em aplicações web consiste na utilização de técnicas, ferramentas e boas práticas capazes de proteger os sistemas contra ataques cibernéticos, acessos não autorizados e vazamentos de dados. Um sistema inseguro pode causar prejuízos financeiros, danos à reputação das empresas e comprometer a privacidade dos usuários.

O PHP é uma das linguagens de programação mais utilizadas no desenvolvimento de aplicações web e disponibiliza diversos recursos voltados à segurança, como funções para criação de hashes de senhas, criptografia de informações, codificação de dados e mecanismos para prevenção de ataques conhecidos. Além disso, bibliotecas como o OpenSSL permitem implementar soluções robustas para proteger informações confidenciais.

Esta pesquisa apresenta os principais conceitos relacionados à segurança em aplicações web utilizando PHP, abordando técnicas de criptografia, hash, codificação, proteção de senhas, prevenção contra ataques e boas práticas recomendadas para o desenvolvimento de sistemas seguros.

---

# 1. Segurança em Aplicações Web

## O que é Segurança da Informação?

Segurança da informação é o conjunto de práticas, tecnologias e procedimentos utilizados para proteger informações contra acessos não autorizados, alterações indevidas, destruição ou indisponibilidade. Seu objetivo é garantir que os dados permaneçam protegidos durante todo o seu ciclo de vida, desde a coleta até o armazenamento e compartilhamento.

A segurança da informação baseia-se em três princípios fundamentais, conhecidos como Tríade CIA:

### Confidencialidade

A confidencialidade garante que apenas pessoas autorizadas tenham acesso às informações. Isso impede que dados sensíveis sejam visualizados por terceiros.

Como exemplo, apenas o proprietário de uma conta bancária deve conseguir visualizar seu saldo e seu extrato.

### Integridade

A integridade garante que os dados permaneçam corretos e completos, impedindo alterações não autorizadas.

Em um sistema escolar, por exemplo, um aluno não pode modificar suas próprias notas.

### Disponibilidade

A disponibilidade garante que as informações estejam acessíveis sempre que forem necessárias para usuários autorizados.

Um sistema hospitalar precisa permanecer disponível para que médicos tenham acesso ao histórico dos pacientes durante emergências.

---

## Por que proteger os dados dos usuários?

As aplicações web armazenam informações extremamente importantes dos usuários, como:

- Nome completo;
- CPF;
- RG;
- Endereço;
- E-mail;
- Número de telefone;
- Senhas;
- Dados bancários;
- Cartões de crédito;
- Histórico de compras.

Caso essas informações sejam roubadas, criminosos podem realizar fraudes financeiras, aplicar golpes, utilizar identidades falsas ou vender esses dados ilegalmente.

Além disso, empresas responsáveis pelo vazamento podem sofrer prejuízos financeiros, perda da confiança dos clientes e sanções legais. No Brasil, a Lei Geral de Proteção de Dados (LGPD) estabelece que organizações devem proteger adequadamente os dados pessoais armazenados.

---

## Principais riscos em aplicações desenvolvidas para Internet

As aplicações web estão constantemente conectadas à Internet e, por isso, tornam-se alvos de diversos ataques.

### SQL Injection

O SQL Injection acontece quando um invasor consegue inserir comandos SQL em campos de entrada da aplicação.

Esses comandos podem permitir acesso indevido ao banco de dados, roubo de informações, alteração de registros ou até exclusão completa das tabelas.

### Cross-Site Scripting (XSS)

O XSS permite que um atacante injete códigos JavaScript maliciosos em páginas da aplicação.

Quando outro usuário acessa essa página, o código é executado automaticamente em seu navegador, podendo roubar cookies, senhas e dados pessoais.

### Cross-Site Request Forgery (CSRF)

Nesse ataque, um usuário autenticado é induzido a executar ações sem perceber, como alterar sua senha ou realizar uma transferência bancária.

Como o navegador já possui uma sessão válida, o servidor acredita que a ação foi realizada pelo próprio usuário.

### Ataques de força bruta

Consistem em testar milhares ou milhões de combinações de senhas automaticamente até descobrir a senha correta.

Quanto mais simples a senha, maior a probabilidade de sucesso.

### Session Hijacking

É o roubo do identificador da sessão do usuário autenticado, permitindo que o invasor utilize sua conta sem conhecer sua senha.

### Malware

Programas maliciosos podem comprometer servidores, computadores e dispositivos dos usuários, roubando informações ou danificando sistemas.

### Vazamento de Dados

Ocorre quando informações confidenciais são expostas devido a falhas de segurança, ataques hackers ou configurações incorretas do sistema.

---

# 2. Criptografia, Hash e Codificação

Embora sejam frequentemente confundidos, criptografia, hash e codificação possuem objetivos completamente diferentes.

| Técnica | Objetivo | Pode ser revertida? | Principal utilização |
|----------|----------|---------------------|----------------------|
| Criptografia | Proteger informações | Sim | Dados confidenciais |
| Hash | Garantir integridade e armazenar senhas | Não | Senhas e validação |
| Codificação | Converter dados para outro formato | Sim | Transmissão de dados |

## Criptografia

A criptografia transforma uma informação legível em um formato ilegível utilizando um algoritmo matemático e uma chave criptográfica.

Somente quem possui a chave correta consegue recuperar a informação original.

Ela é amplamente utilizada para proteger dados durante sua transmissão e armazenamento.

### Exemplo de utilização

- Internet Banking;
- WhatsApp;
- Comércio eletrônico;
- Sistemas hospitalares;
- Aplicativos de mensagens.

Um algoritmo bastante utilizado atualmente é o **AES (Advanced Encryption Standard)**.

### Exemplo em PHP

```php
$texto = "Mensagem Secreta";
$chave = "1234567890123456";

$criptografado = openssl_encrypt(
    $texto,
    "AES-128-ECB",
    $chave
);
```

---
