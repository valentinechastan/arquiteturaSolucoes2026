# 2. Análise dos Princípios Arquiteturais

Sistema analisado: **WhatsApp**

---

# Separação de Responsabilidades

## 1. Diferentes camadas/módulos do sistema

O sistema pode ser interpretado arquiteturalmente dividido em:

* **Camada Cliente (Mobile, Web e Desktop)**
  Interface do usuário, renderização de conversas, captura de mídia e interação.

* **Camada de Comunicação em Tempo Real**
  Responsável pela troca de mensagens entre cliente e servidores.

* **Camada de Autenticação e Identidade**
  Validação de número telefônico, gerenciamento de sessão e dispositivos vinculados.

* **Camada de Criptografia**
  Implementação de criptografia ponta-a-ponta, geração e troca de chaves.

* **Camada de Processamento de Mensagens**
  Roteamento, enfileiramento e confirmação de entrega.

* **Camada de Armazenamento**
  Armazenamento temporário de mensagens não entregues e metadados.

* **Serviços Auxiliares**
  Notificações push, status, grupos, chamadas de voz/vídeo.

---

## 2. Como as responsabilidades estão divididas

Cada camada possui uma responsabilidade bem definida:

* O **cliente** é responsável apenas por interface, criptografia local e envio/recebimento.
* O **servidor** não acessa o conteúdo das mensagens, apenas realiza o roteamento.
* O módulo de **criptografia** é isolado da lógica de interface.
* O serviço de **chamadas** opera separado do serviço de mensagens.
* O módulo de **grupos** gerencia permissões e administração sem interferir na lógica de entrega.

Essa divisão reduz sobreposição de responsabilidades e facilita manutenção.

---

## 3. Exemplos específicos

* A criptografia ocorre no dispositivo antes do envio, demonstrando separação entre segurança e transporte.
* O WhatsApp Web depende da autenticação já estabelecida no dispositivo móvel, separando autenticação de interface.
* O serviço de notificações push funciona independentemente do carregamento completo da conversa.

---

# Coesão

## 1. Análise do agrupamento de funcionalidades

As funcionalidades são, em geral, bem agrupadas:

* Tudo relacionado a mensagens (envio, recebimento, confirmação de leitura) está concentrado no módulo de mensagens.
* Funções de chamadas (voz e vídeo) estão agrupadas em um serviço específico.
* Administração de grupos é centralizada em um módulo próprio.

Isso indica **alta coesão funcional**, pois cada módulo executa tarefas relacionadas entre si.

---

## 2. Exemplos de alta ou baixa coesão

**Alta coesão:**

* Módulo de mensagens, responsável apenas por comunicação textual e entrega.
* Módulo de chamadas, responsável apenas por comunicação em tempo real por áudio e vídeo.

**Possível ponto de menor coesão:**

* O recurso de “Status” compartilha infraestrutura com mensagens, mas possui lógica mais próxima de rede social, o que pode indicar mistura de responsabilidades.

---

## 3. Sugestões de melhoria

* Isolar ainda mais o módulo de Status como serviço independente, reduzindo dependências com o núcleo de mensagens.
* Modularizar de forma mais explícita funcionalidades comerciais (WhatsApp Business) para evitar impacto na experiência do usuário comum.

---

# Acoplamento

## 1. Avaliação do nível de dependência entre componentes

O sistema apresenta **baixo acoplamento entre cliente e servidor**, pois a comunicação ocorre via protocolos definidos e APIs.

Entretanto, há **acoplamento moderado entre o cliente móvel e o WhatsApp Web**, já que o funcionamento da versão web depende da autenticação ativa no dispositivo principal.

---

## 2. Pontos de alto acoplamento identificados

* Dependência do número de telefone como identificador único.
* Dependência inicial do dispositivo móvel para ativação da conta.
* Sincronização entre múltiplos dispositivos pode gerar dependência de estado.

---

## 3. Impacto no sistema

* O acoplamento ao número telefônico limita flexibilidade de identidade digital.
* A dependência inicial do celular impacta a experiência de usuários que desejam uso independente no desktop.
* O acoplamento na sincronização pode gerar inconsistências temporárias em mensagens multi-dispositivo.

Apesar desses pontos, o sistema mantém equilíbrio entre acoplamento e desempenho, priorizando simplicidade operacional e segurança.
