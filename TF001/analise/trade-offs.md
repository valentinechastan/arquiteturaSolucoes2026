# Identificação de Trade-offs

---

## Trade-off 1: Segurança vs Performance

**Decisão tomada:**
Implementação de criptografia ponta-a-ponta em todas as mensagens, chamadas e mídias trocadas entre usuários.

**Justificativa:**
A adoção de criptografia ponta-a-ponta garante que apenas remetente e destinatário tenham acesso ao conteúdo das mensagens. Isso reforça a confiança dos usuários e diferencia o sistema em termos de privacidade e proteção de dados.

**Impacto:**

* Aumento do processamento nos dispositivos durante criptografia e descriptografia.
* Maior consumo de recursos computacionais.
* Pequeno impacto na latência de envio.
* Fortalecimento da reputação do sistema em relação à segurança.

---

## Trade-off 2: Disponibilidade vs Consistência

**Decisão tomada:**
Priorização da entrega rápida de mensagens mesmo que a sincronização entre múltiplos dispositivos ocorra de forma eventual.

**Justificativa:**
Em um sistema global com bilhões de usuários, garantir consistência imediata em todos os dispositivos aumentaria significativamente a complexidade e o custo operacional. A escolha por consistência eventual permite alta disponibilidade e menor tempo de resposta.

**Impacto:**

* Mensagens podem aparecer com pequeno atraso em dispositivos secundários.
* Melhor experiência em termos de rapidez na entrega principal.
* Maior escalabilidade do sistema distribuído.

---

## Trade-off 3: Escalabilidade vs Custo Operacional

**Decisão tomada:**
Uso de infraestrutura distribuída globalmente para reduzir latência e suportar grande volume de conexões simultâneas.

**Justificativa:**
Para atender usuários em diferentes regiões do mundo com baixa latência, é necessário manter servidores distribuídos geograficamente. Isso aumenta custos de infraestrutura, mas garante desempenho adequado.

**Impacto:**

* Elevado investimento em data centers e redes.
* Redução do tempo de resposta nas mensagens.
* Capacidade de suportar picos de uso sem degradação significativa do serviço.

---

## Trade-off 4: Usabilidade vs Privacidade

**Decisão tomada:**
Permitir recursos como backup em nuvem e sincronização multi-dispositivo, mesmo que isso envolva armazenamento adicional de dados fora do dispositivo principal.

**Justificativa:**
Usuários valorizam conveniência e recuperação de conversas ao trocar de aparelho. A oferta de backup melhora a experiência, embora aumente riscos potenciais relacionados à privacidade dependendo da configuração adotada.

**Impacto:**

* Maior facilidade na troca de dispositivos.
* Possível exposição adicional caso serviços de nuvem sejam comprometidos.
* Ampliação do uso do sistema em contextos profissionais e comerciais.
