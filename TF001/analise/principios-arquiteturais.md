# Análise dos Princípios Arquiteturais

Sistema analisado: **WhatsApp**

---

## Separação de Responsabilidades

### Camadas e módulos identificados

O sistema pode ser analisado de forma arquitetural nas seguintes camadas principais:

1. **Camada de Cliente (Frontend)**

   * Aplicativos mobile (Android e iOS)
   * Versão Web
   * Aplicação Desktop

     Responsável por interface, interação com o usuário, exibição de mensagens e gerenciamento local de dados.

2. **Camada de Serviços de Aplicação (Backend)**

   * Servidores de autenticação
   * Servidores de roteamento e entrega de mensagens
   * Serviços de gerenciamento de grupos
   * Serviços de chamadas de voz e vídeo

     Responsável pela lógica de negócio, controle de sessões, gerenciamento de conexões simultâneas e encaminhamento de mensagens.

3. **Camada de Armazenamento**

   * Armazenamento temporário de mensagens não entregues
   * Metadados de conta e grupos

     Responsável pela persistência de dados necessários para funcionamento e recuperação de informações.

4. **Camada de Segurança**

   * Implementação da criptografia ponta-a-ponta
   * Gerenciamento de chaves criptográficas
     Responsável exclusivamente pela proteção do conteúdo das mensagens.

---

### Divisão de responsabilidades

A responsabilidade da interface e experiência do usuário está isolada no cliente.
A responsabilidade de entrega e roteamento de mensagens está concentrada nos servidores.
A responsabilidade de segurança é tratada de forma independente através da criptografia ponta-a-ponta, impedindo que o servidor tenha acesso ao conteúdo das mensagens.

Exemplo específico:

* O aplicativo cifra a mensagem antes do envio.
* O servidor apenas roteia o conteúdo criptografado.
* O dispositivo do destinatário realiza a descriptografia.

Essa divisão reduz riscos de vazamento de dados e permite escalabilidade independente entre interface e infraestrutura.

---

## Coesão

### Análise do agrupamento de funcionalidades

O sistema apresenta, de modo geral, **alta coesão funcional** nos seguintes pontos:

* O módulo de mensagens concentra apenas funcionalidades relacionadas a envio, recebimento, confirmação de leitura e sincronização.
* O módulo de chamadas concentra apenas funcionalidades relacionadas a comunicação em tempo real (voz e vídeo).
* O módulo de grupos concentra gerenciamento de participantes, permissões e administração.

Cada conjunto de funcionalidades possui um propósito claro e bem definido.

---

### Exemplos de alta coesão

* O serviço de autenticação trata exclusivamente login, verificação de número e validação de sessão.
* O serviço de gerenciamento de grupos trata apenas criação, remoção de membros e permissões administrativas.

---

### Possível ponto de melhoria

A funcionalidade de “Status” possui comportamento semelhante a uma rede social, diferente da função principal de mensageria. Isso pode indicar menor coesão conceitual dentro do sistema como um todo.

Uma possível melhoria seria isolar arquiteturalmente o serviço de Status como um serviço independente, reduzindo impacto estrutural sobre o núcleo de mensagens.

---

## Acoplamento

### Nível de dependência entre componentes

O sistema apresenta **baixo acoplamento entre cliente e servidor**, pois a comunicação ocorre por meio de protocolos bem definidos e APIs específicas.

O cliente depende do backend para:

* Autenticação
* Sincronização
* Entrega de mensagens

Entretanto, o backend não depende da interface específica utilizada (mobile, web ou desktop), o que demonstra desacoplamento da camada de apresentação.

---

### Pontos de maior acoplamento

* A sincronização multi-dispositivo exige forte integração entre controle de sessão, armazenamento temporário e roteamento de mensagens.
* O sistema de chamadas depende de integração direta com serviços de rede em tempo real, aumentando a complexidade e dependência entre módulos.

---

### Impacto do acoplamento no sistema

Alto acoplamento pode dificultar evolução e manutenção.
No caso do WhatsApp, o uso de arquitetura distribuída e divisão clara de responsabilidades reduz esse risco, permitindo:

* Escalabilidade horizontal
* Atualizações independentes de componentes
* Menor impacto de falhas isoladas

De forma geral, o sistema apresenta boa aplicação dos princípios de separação de responsabilidades, alta coesão nos módulos principais e controle adequado de acoplamento, considerando sua complexidade e escala global.
