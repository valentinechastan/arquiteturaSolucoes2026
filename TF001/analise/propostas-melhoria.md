# 5. Proposta de Melhoria

---

## Proposta 1 – Arquitetura de sincronização multi-dispositivo mais desacoplada

### Problema identificado

A sincronização entre múltiplos dispositivos pode apresentar atrasos temporários, especialmente quando há troca frequente entre celular, web e desktop. Isso indica forte dependência entre controle de sessão, roteamento de mensagens e armazenamento temporário.

### Proposta de solução

Implementação de um serviço dedicado exclusivamente à sincronização de estado entre dispositivos, baseado em eventos (event-driven architecture), separado do serviço principal de entrega de mensagens.

Esse serviço seria responsável por:

* Gerenciar estado de leitura
* Sincronizar histórico recente
* Atualizar metadados entre dispositivos
* Reduzir dependência direta entre cliente secundário e dispositivo principal

### Benefícios esperados

* Redução de inconsistências temporárias
* Melhor experiência ao alternar entre dispositivos
* Maior modularidade arquitetural
* Possibilidade de evolução independente do mecanismo de sincronização

### Trade-offs da proposta

* Aumento da complexidade arquitetural
* Maior custo operacional com novo serviço dedicado
* Necessidade de monitoramento adicional

---

## Proposta 2 – Serviço independente para funcionalidades sociais (Status e Comunidades)

### Problema identificado

Funcionalidades como Status e Comunidades possuem comportamento semelhante ao de redes sociais, diferente do núcleo de mensageria. Isso pode reduzir a coesão conceitual da arquitetura principal.

### Proposta de solução

Isolar arquiteturalmente essas funcionalidades em um serviço independente, com APIs próprias e banco de dados separado, mantendo integração com o sistema principal apenas por meio de contratos bem definidos.

### Benefícios esperados

* Aumento da coesão do núcleo de mensagens
* Redução de impacto de falhas sociais no serviço principal
* Escalabilidade independente para recursos com padrões de uso diferentes
* Facilidade de evolução dessas funcionalidades sem afetar a base de mensageria

### Trade-offs da proposta

* Maior número de serviços para gerenciar
* Aumento de custos de infraestrutura
* Necessidade de controle rigoroso de comunicação entre serviços

As propostas apresentadas buscam melhorar modularidade, escalabilidade e organização arquitetural, mantendo viabilidade técnica e considerando os impactos estruturais envolvidos.
