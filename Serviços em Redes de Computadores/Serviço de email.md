# Conceito
O serviço de email é um componentes fundamentais em redes de computadores, permitindo a troca de mensagens eletrônicas entre usuários. Sua implementação pode ser complexa e requer conhecimentos técnicos específicos. Pode ser implantado internamente ou utilizando serviços de terceiros, sendo uma preocupação significativa em relação à segurança da informação.
# Características
- **Alta Disponibilidade:** Deve estar disponível a qualquer momento.
- **Mobilidade:** Acesso ao email de qualquer dispositivo.
- **Opções de Armazenamento:** Variadas formas de armazenar mensagens.
- **Escalabilidade:** Capacidade de aumentar recursos conforme a necessidade.
# Protocolos de email
1. **SMTP (Simple Mail Transfer Protocol)**
	1. **Porta Padrão:** 25 (também usa 587 com STARTTLS ou 465 com SSL/TLS para segurança).
	2. **Função:** Envio de emails entre servidores.
2. **POP (Post Office Protocol)**
	1. **Porta Padrão:** 110 (995 para POP3 com SSL/TLS).
	2. **Função:** Recebimento de emails. Baixa as mensagens para o dispositivo local e remove do servidor.
	3. **Modelo:** Caixa de correio offline.
3. **IMAP (Internet Message Access Protocol)**
	1. **Porta:** 143 (993 para conexões criptografadas via SSL).
	2. **Função:** Acesso remoto às caixas de correio, mantendo as mensagens no servidor e exibindo em tempo real.
	3. **Recursos:** Sincronização de pastas e status, suporte a múltiplos dispositivos simultâneos, armazenamento no servidor.
# Fluxo de funcionamento do email
1. **MUA (Mail User Agent):** Cliente de email do usuário remetente.
2. **SMTP:** Envia o email do cliente para o servidor remetente.
3. **Servidor de email remetente:** Recebe e processa a mensagem.
4. **Servidor de email destinatário:** Recebe a mensagem.
5. **IMAP ou POP3:** Permite ao cliente destinatário acessar a mensagem.
6. **MUA:** Cliente do email do usuário destinatário recebe a mensagem.
# Componentes
- **MUA (Mail User Agent):** Trata-se do programa ou aplicativo cliente que permite enviar, receber e gerenciar mensagens de email. Fornecem uma interface amigável e recursos avançados para facilitar o uso e a gestão de mensagens de email pelos usuários.
- **MTA (Mail Transfer Agent):** Software responsável pelo roteamento e entrega de mensagens de email entre servidores de email. Também podem realizar outras funções, como armazenamento temporário de mensagens em caso de indisponibilidade do servidor de destino, enfileiramento de mensagens para entrega em momentos específicos, registro de atividades e gerenciamento de erros de entrega.
- **MDA (Mail Delivery Agent):** Componente do sistema de email (atua em conjunto com o MTA): Responsável pela entrega das mensagens de email nas caixas de correio dos destinatários, ou seja, lida com a entrega final das mensagens aos destinatários. O MTA entrega a mensagem ao MDA que verifica a autenticidade e a validade do destinatário, aplica regras específicas de entrega e a notificação de entrega.