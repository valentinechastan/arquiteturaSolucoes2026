# TF001 - Análise Arquitetural: WhatsApp

## Alunos
- **Nome:** Valentine Louise de Chastan Bisanson Santos
- **RA:** 6326033
- **Nome:** Renan Gabriel Oliveira da Silva
- **RA:** 6326093
- **Curso:** Análise e Desenvolvimento de Sistemas

---

## Sistema Analisado

* **Nome:** WhatsApp
* **Categoria:** Aplicação de Mensageria Instantânea
* **Plataforma:** Mobile, Web e Desktop
* **Justificativa da Escolha:**
  O sistema foi escolhido por sua ampla utilização global, alta complexidade arquitetural e necessidade de lidar com escalabilidade massiva, segurança avançada (criptografia ponta-a-ponta) e alta disponibilidade em tempo real.

---

## Estrutura da Análise

### 📋 Descrição do Sistema

* Propósito e funcionamento da plataforma
* Funcionalidades principais
* Perfis de usuários e escala global
* Contexto de uso em dispositivos mobile, web e desktop

---

### 🏗️ Princípios Arquiteturais

* Separação de responsabilidades entre cliente, backend, armazenamento e segurança
* Análise de coesão dos módulos principais (mensagens, chamadas, grupos)
* Avaliação do nível de acoplamento entre componentes e serviços

---

### ⚖️ Trade-offs Identificados

* Segurança vs Performance
* Disponibilidade vs Consistência
* Escalabilidade vs Custo Operacional
* Usabilidade vs Privacidade

---

### 📊 Requisitos Não Funcionais

* Performance sob alta carga
* Escalabilidade horizontal
* Alta disponibilidade global
* Segurança baseada em criptografia ponta-a-ponta
* Usabilidade e simplicidade de interface

---

### 💡 Propostas de Melhoria

* Criação de um serviço dedicado à sincronização multi-dispositivo para reduzir inconsistências e aumentar modularidade
* Isolamento arquitetural das funcionalidades sociais (Status e Comunidades) para aumentar coesão e escalabilidade independente

---

## Diagramas
- `diagramas/arquitetura-atual.png` - Representação interpretativa da arquitetura atual
- `diagramas/arquitetura-proposta.png` - Proposta arquitetural com melhorias sugeridas

---

## Como Navegar

1. Leia a descrição do sistema em `analise/descricao-sistema.md`
2. Consulte os princípios arquiteturais em `analise/principios-arquiteturais.md`
3. Analise os trade-offs identificados em `analise/trade-offs.md`
4. Avalie os requisitos não funcionais em `analise/requisitos-nao-funcionais.md`
5. Verifique as propostas de melhoria em `analise/propostas-melhoria.md`

---

## Conclusões

A análise evidencia que o WhatsApp possui uma arquitetura distribuída, orientada a serviços, projetada para alta escalabilidade e disponibilidade global. 

Observamos forte aplicação de separação de responsabilidades, alta coesão nos módulos funcionais e baixo acoplamento entre camadas, especialmente entre cliente e serviços backend.

Os principais desafios arquiteturais envolvem equilíbrio entre segurança, performance e custo operacional, demonstrando a presença constante de trade-offs estratégicos.

Concluímos que a arquitetura do sistema é madura e robusta, porém apresenta oportunidades de evolução em sincronização multi-dispositivo e gestão de armazenamento distribuído.
