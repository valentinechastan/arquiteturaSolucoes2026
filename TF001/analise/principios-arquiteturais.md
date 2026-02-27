## Separação de Responsabilidades

Podemos identificar:

* Front-end (App Mobile / Web)
* API Gateway
* Servidores de Mensagens
* Serviço de Criptografia
* Banco de Dados
* Serviço de Notificações

Cada módulo tem função específica:

* Front → Interface
* Servidores → roteamento
* Banco → armazenamento
* Criptografia → segurança ponta a ponta

Isso demonstra clara divisão de responsabilidades.

---

## Coesão

Alta coesão:

* Módulo de mensagens cuida apenas de mensagens
* Módulo de chamadas cuida apenas de chamadas

Não mistura pagamento, e-commerce ou rede social dentro do mesmo núcleo.

---

## Acoplamento

Relativamente baixo:

* O cliente não sabe detalhes do banco
* Usa APIs intermediárias
* Criptografia é separada da interface

Possível ponto de alto acoplamento:

* Dependência forte da infraestrutura centralizada do Meta
