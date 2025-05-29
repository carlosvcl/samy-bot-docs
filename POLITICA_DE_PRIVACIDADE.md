# Política de Privacidade do Bot Samy

**Última Atualização:** `29 de Maio de 2025`

Esta Política de Privacidade descreve como o bot Samy, operado por `Carlos Gomes`, coleta, usa, armazena e protege as informações quando você interage com nosso Bot no Discord. A sua privacidade é importante para nós. Ao usar o Samy, você concorda com a coleta e uso de informações de acordo com esta política.

## 1. Informações que Coletamos

Para fornecer e melhorar suas funcionalidades, o Samy pode coletar e armazenar os seguintes tipos de informações:

   a. **Informações Fornecidas pelo Discord e Coletadas Automaticamente:**
      * **IDs do Discord:** Seu ID de Usuário Discord, IDs dos Servidores (Guild IDs) onde o Samy está, IDs dos Canais onde os comandos são usados. Estes são essenciais para o funcionamento do Bot.
      * **Nomes de Usuário e Tags Discord:** Usados para identificação em comandos, leaderboards, mensagens, etc. Samy pode atualizar seu nome de usuário armazenado se você o alterar no Discord.
      * **Conteúdo de Comandos e Interações:** O texto dos comandos que você envia ao Samy e os argumentos fornecidos (ex: nome de música, pergunta para a IA, mensagem de lembrete, configurações de automod).
      * **Metadados de Mensagens:** Timestamp da mensagem e autor da mensagem (para processamento de comandos, cooldowns e logs de moderação).

   b. **Dados Específicos de Funcionalidades (armazenados em nosso banco de dados MongoDB):**
      * **Perfis de Usuário (`userSchema`):**
          * Dados de Economia: Saldo de moedas (carteira e banco), inventário de itens (IDs dos itens e quantidades), XP, nível.
          * Timestamps de Cooldowns de Ação: `dailyLastClaimed`, `workLastClaimed`, `mineLastClaimed`, `lastMessageXpTimestamp`, `lastCollectedTimestamps` (para renda passiva de diferentes fontes, como IDs de itens geradores).
          * Detalhes de Investimentos Ativos: Principal, data de início, duração, taxa de retorno, ID do investimento.
          * Boosts Ativos: Tipo de boost, valor do efeito, tempo de expiração, usos restantes, escopo do comando afetado.
          * Apelido Customizado no Bot (se usado): `customBotDisplayName`.
          * Estatísticas de Usuário (se implementado e habilitado): Contagem de mensagens, comandos usados, etc.
          * Preferências do Usuário (se implementado e habilitado): Ex: notificações por DM.
      * **Logs de Moderação (`moderationLogSchema`):** Tipo de ação (ban, kick, mute, warn, etc.), ID do usuário alvo, ID do moderador que aplicou a ação, razão fornecida, duração (se aplicável), timestamp e ID do caso de moderação.
      * **Lembretes (`reminderSchema`, se implementado):** Conteúdo da mensagem do lembrete, tempo para o lembrete, ID do alvo (usuário, canal, cargo), ID do usuário que criou o lembrete.
      * **Dados de Gamificação (se implementado):** Conquistas desbloqueadas, pontos de reputação, dados de quizzes/flashcards.
      * **Sessões de Chat com IA (Gemini):** Para funcionalidades de chat contínuo (`s!chat`), o histórico da conversa da sessão atual (mensagens do usuário e respostas da IA) é armazenado temporariamente enquanto a sessão estiver ativa para manter o contexto com a IA. Este histórico é específico para o usuário e o canal e é descartado quando a sessão é explicitamente terminada com `s!chat end` ou após um período de inatividade programado. `[SE VOCÊ PLANEJA ARMAZENAR PROMPTS/RESPOSTAS DE IA DE FORMA MAIS PERSISTENTE PARA ANÁLISE OU MELHORIA, SEJA TRANSPARENTE AQUI: explique como, por quanto tempo, se será anonimizado, e qual o propósito. Obtenha consentimento se necessário.]`

   c. **Dados de Uso Agregados e Anônimos:**
      Podemos coletar dados sobre como o Bot é usado (ex: comandos mais populares, frequência de uso de funcionalidades) de forma agregada e anônima para melhorar o serviço. Estes dados não identificam usuários individualmente.

## 2. Como Usamos as Informações Coletadas

Utilizamos as informações coletadas para os seguintes propósitos:
   a. **Fornecer e Operar as Funcionalidades do Bot:** Processar seus comandos, gerenciar seu perfil de economia, aplicar moderação conforme configurado pelos administradores do servidor, enviar lembretes agendados, facilitar jogos e interações com a IA, etc.
   b. **Manter e Melhorar o Bot:** Diagnosticar problemas técnicos, corrigir bugs, analisar o uso para otimizar o desempenho e desenvolver novas funcionalidades.
   c. **Personalizar a Experiência:** Usar seu nome de usuário, apelido customizado (se definido) e outras preferências para tornar as interações mais personalizadas.
   d. **Suporte ao Usuário:** Ajudar a resolver problemas ou responder a perguntas que você possa ter sobre o uso do Bot.
   e. **Comunicação (Opcional):** Podemos usar um canal de anúncios no servidor de suporte (se você fizer parte dele) para informar sobre atualizações importantes do Bot. Não enviaremos DMs não solicitadas para marketing.

## 3. Compartilhamento e Divulgação de Dados

   a. **Nós não vendemos, alugamos ou trocamos suas informações pessoais com terceiros para fins de marketing.**
   b. **APIs de Terceiros:** Para algumas funcionalidades, o Samy interage com APIs de terceiros. Apenas as informações estritamente necessárias para a funcionalidade são trocadas. O uso dessas APIs está sujeito às suas respectivas políticas de privacidade. Os principais serviços de terceiros que o Samy pode usar incluem:
        * **Google Generative AI (Gemini):** Para comandos de IA (`s!ask`, `s!chat`, etc.). Sua pergunta/prompt é enviada para a API.
        * **OpenWeatherMap API:** Para o comando de clima (`s!weather`). O nome da cidade é enviado.
        * **YouTube Data API v3 (via `googleapis`):** Para busca de músicas no comando `s!search`. Sua query de busca é enviada.
        * **Plataformas de Música (via `discord-player` e seus extratores):** Para buscar e tocar músicas (YouTube, SoundCloud, etc.). Queries de busca ou URLs são enviadas.
        * **Genius API (ou similar):** Para o comando de letras (`s!lyrics`). O nome da música/artista é enviado.
        * **Piston API (ou similar):** Para execução de código no comando `s!code`. O código e a linguagem são enviados.
   c. **Logs de Moderação:** São geralmente visíveis para administradores e moderadores do servidor onde a ação ocorreu, para fins de transparência e gerenciamento do servidor.
   d. **Informações Públicas no Discord:** Seu nome de usuário, avatar, e mensagens enviadas em canais públicos (incluindo comandos para o Samy e suas respostas) são inerentemente visíveis para outros usuários no Discord. Leaderboards e resultados de jogos também podem ser públicos dentro do servidor.
   e. **Obrigações Legais e Segurança:** Podemos divulgar suas informações se formos obrigados por lei, ou se acreditarmos de boa fé que tal ação é necessária para proteger nossos direitos, sua segurança ou a segurança de outros, investigar fraudes ou responder a uma solicitação governamental.

## 4. Retenção e Exclusão de Dados

   a. **Dados de Perfil do Usuário:** Seus dados de perfil (economia, XP, inventário, etc.) são mantidos enquanto você utiliza o Bot em um servidor ou até que você solicite a exclusão dos seus dados (ver seção "Seus Direitos").
   b. **Logs de Moderação:** São mantidos enquanto o servidor existir ou conforme a política de retenção do servidor, pois são registros importantes para a administração do servidor.
   c. **Lembretes:** São excluídos do nosso banco de dados após serem enviados com sucesso ou se expirarem sem envio (se aplicável).
   d. **Como Solicitar a Exclusão dos Seus Dados:** Você pode solicitar a exclusão dos seus dados pessoais armazenados pelo Samy (seu perfil de usuário no nosso banco de dados) entrando em contato conosco através de `samybot25@gmail.com`. Faremos o possível para atender à sua solicitação, sujeito a quaisquer obrigações legais ou necessidades operacionais de retenção (ex: logs de moderação que são registros do servidor).
   e. **Remoção do Bot de um Servidor:** Se o Samy for removido de um servidor, os dados de configuração específicos daquele servidor para o bot podem ser removidos. Os perfis de usuário são geralmente globais (baseados no ID do Discord do usuário), então seu perfil de economia, etc., persistirá se você usar o Samy em outros servidores.
## 5. Segurança dos Dados

   Levamos a segurança dos seus dados a sério e implementamos medidas técnicas e administrativas razoáveis para proteger as informações que coletamos contra acesso não autorizado, alteração, divulgação ou destruição. As chaves de API e credenciais de banco de dados são armazenadas de forma segura usando variáveis de ambiente. Utilizamos MongoDB Atlas para armazenamento de banco de dados, que oferece seus próprios recursos de segurança. No entanto, nenhum método de transmissão pela Internet ou de armazenamento eletrônico é 100% seguro.

## 6. Seus Direitos de Privacidade (Exemplo, pode variar por região)

   Dependendo da sua jurisdição (ex: GDPR para usuários na Europa, LGPD para usuários no Brasil), você pode ter certos direitos em relação aos seus dados pessoais. Isso pode incluir:
   * O direito de acessar os dados pessoais que temos sobre você.
   * O direito de corrigir informações imprecisas.
   * O direito de solicitar a exclusão de seus dados pessoais (o "direito de ser esquecido").
   * O direito de restringir o processamento de seus dados.
   * O direito à portabilidade dos dados.
   Para exercer esses direitos, entre em contato conosco usando as informações de contato fornecidas.

## 7. Privacidade de Crianças

   O Samy não se destina e não coleta intencionalmente informações de crianças menores de 13 anos (ou a idade mínima aplicável em sua jurisdição e conforme os Termos de Serviço do Discord). Se você acredita que coletamos informações de uma criança, entre em contato conosco imediatamente para que possamos tomar as medidas apropriadas.

## 8. Alterações nesta Política de Privacidade

   Podemos atualizar nossa Política de Privacidade periodicamente. Notificaremos você sobre quaisquer alterações publicando a nova Política de Privacidade em `` e atualizando a data da "Última Atualização" no topo desta política. É aconselhável que você revise esta Política periodicamente para quaisquer alterações.

## 9. Contato

   Se você tiver alguma dúvida ou preocupação sobre esta Política de Privacidade ou nossas práticas de dados, entre em contato conosco:
   * `E-mail: samybot25@gmail.com, ou Servidor de Suporte no Discord: https://discord.gg/haQPSP4EPR, ou Comando no Bot: s!support privacy`

---
Ao usar o Bot Samy, você indica sua aceitação desta Política de Privacidade e dos nossos [Termos de Serviço]([https://github.com/carlosvcl/samy-bot-docs/blob/main/TERMOS_DE_SERVICO.md]).
