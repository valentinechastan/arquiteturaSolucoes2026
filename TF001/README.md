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
- Funcionalidades principais
- Perfis de usuários
- Contexto de uso
- Complexidade operacional

### 🏗️ Princípios Arquiteturais
- Separação de responsabilidades
- Análise de coesão
- Avaliação de acoplamento
- Organização em camadas e serviços

### ⚖️ Trade-offs Identificados
- Segurança vs Performance
- Disponibilidade vs Consistência
- Usabilidade vs Privacidade
- Escalabilidade vs Custo Operacional

### 📊 Requisitos Não Funcionais
- Performance
- Escalabilidade
- Disponibilidade
- Segurança
- Usabilidade
- Confiabilidade

### 💡 Propostas de Melhoria
- Problema identificado 1
- Problema identificado 2
- Soluções arquiteturais propostas
- Análise dos trade-offs das melhorias

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
