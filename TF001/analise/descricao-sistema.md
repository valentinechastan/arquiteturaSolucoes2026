# 1. Descrição do Sistema

## 1.1 Nome e Propósito do Sistema

O sistema analisado é o **WhatsApp**, uma plataforma global de comunicação instantânea pertencente à Meta Platforms.

Seu principal propósito é permitir a comunicação rápida, segura e de baixo custo entre usuários por meio de mensagens de texto, chamadas de voz, chamadas de vídeo e compartilhamento de mídia, utilizando conexão com a internet em vez da infraestrutura tradicional de SMS e telefonia.

O sistema foi projetado para operar em escala global, atendendo bilhões de usuários simultaneamente, com alta disponibilidade e baixa latência.

---

## 1.2 Principais Funcionalidades

O WhatsApp oferece um conjunto robusto de funcionalidades que exigem uma arquitetura distribuída e altamente escalável:

* Envio e recebimento de mensagens instantâneas individuais e em grupo
* Criptografia ponta-a-ponta baseada no Signal Protocol
* Chamadas de voz e vídeo individuais e em grupo
* Compartilhamento de imagens, vídeos, documentos, localização e áudios
* Criação e gerenciamento de grupos e comunidades
* Sincronização multi-dispositivo (uso simultâneo em celular, navegador e desktop)
* Versão empresarial através do **WhatsApp Business**, permitindo catálogos, respostas automáticas e integração com APIs

Cada uma dessas funcionalidades implica desafios arquiteturais relacionados a escalabilidade, segurança, armazenamento distribuído e entrega confiável de mensagens.

---

## 1.3 Tipos de Usuários

O sistema atende diferentes perfis de usuários:

### Usuários Individuais

* Pessoas físicas que utilizam o aplicativo para comunicação pessoal
* Representam a maior parte da base de usuários (bilhões globalmente)
* Demandam simplicidade, rapidez e segurança

### Administradores de Grupos e Comunidades

* Usuários responsáveis por gerenciar grupos grandes
* Precisam de ferramentas de controle, moderação e organização

### Usuários Comerciais

* Empresas que utilizam o **WhatsApp Business**
* Demandam integração com sistemas externos, automação e APIs
* Necessitam maior confiabilidade e disponibilidade contínua

Essa diversidade de perfis impacta diretamente a arquitetura, pois o sistema precisa suportar diferentes níveis de uso e carga operacional.

---

## 1.4 Contexto de Uso

O WhatsApp é um sistema multiplataforma, disponível em:

* Dispositivos móveis (Android e iOS)
* Navegadores web (WhatsApp Web)
* Aplicações desktop para Windows e macOS

![Image](https://www.sketchappsources.com/resources/source-image/whatsapp-ui-android-abinashmohanty.png)

![Image](https://s3-alpha.figma.com/hub/file/2218469377140533285/c55d1452-244a-47c7-94c8-d21e42dd11a2-cover.png)

![Image](https://user-images.githubusercontent.com/44744039/224526456-40c82430-70cb-44e3-82ac-182efde8255f.png)

![Image](https://user-images.githubusercontent.com/44744039/224526440-b4eb6a54-4dda-430c-a681-286f5b406fe7.png)

O uso ocorre majoritariamente em dispositivos móveis, caracterizando um ambiente de:

* Conectividade variável (redes móveis instáveis)
* Necessidade de baixa latência
* Alta concorrência de usuários simultâneos
* Operação contínua 24 horas por dia

Além disso, o sistema precisa lidar com:

* Sincronização entre múltiplos dispositivos
* Entrega assíncrona de mensagens
* Armazenamento temporário quando o destinatário está offline
* Garantia de integridade e confidencialidade dos dados transmitidos

---

## 1.5 Complexidade Operacional

Do ponto de vista arquitetural, o WhatsApp apresenta elevada complexidade operacional devido a:

* Escala global com bilhões de contas ativas
* Milhões de conexões simultâneas
* Necessidade de alta disponibilidade
* Processamento criptográfico em larga escala
* Infraestrutura distribuída geograficamente

A arquitetura precisa equilibrar:

* Performance
* Segurança
* Escalabilidade
* Custo operacional

Esses fatores tornam o sistema adequado para uma análise arquitetural aprofundada, pois envolve desafios reais de sistemas distribuídos, consistência de dados, tolerância a falhas e engenharia de software em larga escala.
