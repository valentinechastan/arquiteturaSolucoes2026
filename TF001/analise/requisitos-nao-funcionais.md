# Análise de Requisitos Não Funcionais

---

## Performance

O sistema apresenta baixa latência na entrega de mensagens, mesmo sob alta carga de usuários simultâneos. Em condições normais de rede, mensagens de texto são entregues quase instantaneamente.

A performance é sustentada por:

* Infraestrutura distribuída globalmente
* Uso de conexões persistentes para troca de mensagens
* Armazenamento temporário apenas quando o destinatário está offline

Sob picos de uso (eventos globais ou instabilidades regionais), podem ocorrer atrasos temporários na entrega, mas o sistema tende a manter funcionamento parcial em vez de interrupção total.

De forma geral, atende adequadamente ao requisito de alto desempenho para comunicação em tempo real.

---

## Escalabilidade

O sistema suporta mais de 2 bilhões de usuários ativos, o que demonstra alta escalabilidade.

A escalabilidade ocorre principalmente por:

* Arquitetura distribuída
* Balanceamento de carga entre servidores
* Escalabilidade horizontal (adição de novos servidores conforme aumento de demanda)

A estrutura permite crescimento contínuo da base de usuários sem necessidade de reestruturação completa da arquitetura.

O modelo adotado é adequado para crescimento global contínuo.

---

## Disponibilidade

O sistema apresenta alta disponibilidade, funcionando 24 horas por dia em escala global.

Embora ocorram interrupções ocasionais, estas são relativamente raras considerando o volume de usuários atendidos. A arquitetura distribuída reduz pontos únicos de falha e permite recuperação relativamente rápida em casos de instabilidade.

A priorização da disponibilidade é evidente na decisão de permitir consistência eventual em sincronizações, garantindo que o serviço principal (envio e recebimento de mensagens) continue operando.

---

## Segurança

O sistema utiliza criptografia ponta-a-ponta, garantindo que apenas remetente e destinatário tenham acesso ao conteúdo das mensagens.

Medidas de segurança incluem:

* Criptografia de mensagens e chamadas
* Verificação de identidade por número telefônico
* Confirmação em duas etapas
* Controle de privacidade para foto, status e última visualização

O modelo reduz riscos de interceptação de conteúdo, embora metadados (como horários e contatos) ainda possam ser processados pelo sistema para funcionamento do serviço.

O requisito de segurança é atendido de forma robusta para o padrão de aplicações de mensageria.

---

## Usabilidade

A interface é simples e intuitiva, exigindo pouco aprendizado inicial.

Características que favorecem usabilidade:

* Cadastro baseado apenas em número de telefone
* Interface organizada por conversas
* Indicadores visuais claros de envio, entrega e leitura
* Integração direta com agenda de contatos

A curva de aprendizado é baixa, permitindo uso por diferentes faixas etárias e níveis de familiaridade tecnológica.

O sistema atende fortemente ao requisito de usabilidade, sendo um dos fatores centrais de sua ampla adoção global.
