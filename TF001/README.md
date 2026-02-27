# TF001 - Análise Arquitetural: WhatsApp

## Alunos
- **Nome:** Valentine Louise de Chastan Bisanson Santos
- **RA:** 6326033
- **Nome:** Renan
- **RA:** 0000000
- **Curso:** Análise e Desenvolvimento de Sistemas

---

## Sistema Analisado
- **Nome:** WhatsApp
- **Categoria:** Comunicação / Mensageria Instantânea
- **Plataforma:** Mobile (Android/iOS), Web e Desktop
- **Justificativa da Escolha:**
Escolhemos o WhatsApp por ser um sistema de grande escala, utilizado globalmente por bilhões de usuários, apresentando desafios arquiteturais relevantes como alta disponibilidade, escalabilidade massiva, criptografia ponta a ponta e comunicação em tempo real.

---

## Estrutura da Análise

### 📋 Descrição do Sistema

* Envio e recebimento de mensagens instantâneas com criptografia ponta-a-ponta
* Chamadas de voz e vídeo individuais e em grupo
* Criação e gerenciamento de grupos e comunidades
* Compartilhamento de mídia (imagens, vídeos, documentos e áudios)
* Sincronização de conversas entre dispositivos (multi-dispositivo)
* Perfis de usuários individuais, administradores de grupos e contas comerciais (WhatsApp Business)
* Utilização global em contextos pessoais, profissionais e comerciais, com alta demanda de disponibilidade e baixa latência

---

### 🏗️ Princípios Arquiteturais

* Aplicação de separação de responsabilidades entre clientes (mobile/web), servidores de mensagens e serviços de armazenamento
* Alta coesão nos serviços responsáveis por autenticação, entrega de mensagens e gerenciamento de grupos
* Baixo acoplamento entre componentes por meio de APIs e comunicação baseada em serviços
* Estrutura distribuída para suportar milhões de conexões simultâneas
* Uso de criptografia ponta-a-ponta como responsabilidade isolada no processo de envio e recebimento de mensagens

---

### ⚖️ Trade-offs Identificados

* Segurança vs Performance: a criptografia ponta-a-ponta aumenta a proteção dos dados, mas adiciona processamento extra
* Disponibilidade vs Consistência: priorização da entrega rápida de mensagens mesmo em cenários de sincronização eventual entre dispositivos
* Escalabilidade vs Custo Operacional: necessidade de infraestrutura global distribuída para manter baixa latência
* Usabilidade vs Privacidade: recursos como backup em nuvem aumentam conveniência, mas podem reduzir o nível de proteção dos dados

---

### 📊 Requisitos Não Funcionais

* Alta performance com baixa latência na entrega de mensagens
* Escalabilidade horizontal para suportar bilhões de usuários
* Alta disponibilidade com mínima interrupção do serviço
* Segurança baseada em criptografia ponta-a-ponta
* Usabilidade simples e intuitiva
* Confiabilidade na entrega e sincronização de mensagens

---

### 💡 Propostas de Melhoria

* Implementação de mecanismos mais avançados de moderação automatizada em grupos grandes, mantendo o equilíbrio entre privacidade e controle
* Aprimoramento da sincronização multi-dispositivo para reduzir inconsistências temporárias de mensagens
* Adoção de estratégias adicionais de observabilidade e monitoramento distribuído para antecipar falhas
* Otimização do consumo de recursos em chamadas de vídeo para melhorar desempenho em redes instáveis

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
