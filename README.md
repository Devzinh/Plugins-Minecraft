# DevTicket - Sistema Avançado de Tickets

![DevTicket Logo](https://img.shields.io/badge/DevTicket-blue.svg)
![Minecraft](https://img.shields.io/badge/Minecraft-1.18.2-green.svg)
![Java](https://img.shields.io/badge/Java-17-orange.svg)

Um sistema completo e avançado de tickets para servidores Minecraft, desenvolvido para oferecer suporte eficiente aos jogadores com interface moderna e recursos profissionais.

## 🚀 Características Principais

### ✨ Interface Moderna
- **GUI Interativa**: Interface gráfica intuitiva e moderna
- **Navegação Fluida**: Menus organizados e fáceis de usar
- **Design Responsivo**: Adaptável a diferentes necessidades

### 🗄️ Sistema de Banco de Dados
- **SQLite**: Banco local para servidores pequenos/médios
- **MySQL**: Suporte para servidores grandes com banco remoto
- **Pool de Conexões**: Gerenciamento eficiente com HikariCP
- **Backup Automático**: Proteção dos dados

### 📋 Categorias e Prioridades
- **Categorias Personalizáveis**: Suporte Técnico, Denúncias, Sugestões, Bug Reports
- **Sistema de Prioridades**: Baixa, Média, Alta, Urgente
- **Roteamento Inteligente**: Direcionamento automático por categoria

### 👥 Gerenciamento Avançado
- **Atribuição de Tickets**: Sistema de responsabilidade por staff
- **Status Dinâmicos**: Aberto, Em Andamento, Fechado
- **Histórico Completo**: Rastreamento de todas as ações
- **Sistema de Comentários**: Comunicação em tempo real

### 🔔 Notificações Inteligentes
- **Alertas para Staff**: Notificações de novos tickets
- **Integração Discord**: Webhooks para notificações externas
- **Tickets Antigos**: Alertas para tickets sem resposta
- **Fechamento Automático**: Limpeza de tickets inativos

### 🛡️ Segurança e Controle
- **Sistema de Cooldown**: Prevenção de spam
- **Limites por Jogador**: Controle de quantidade de tickets
- **Permissões Granulares**: Controle detalhado de acesso
- **Logs Completos**: Auditoria de todas as ações

## 📦 Instalação

1. **Baixe** o arquivo `DevTicket.jar`
2. **Coloque** na pasta `plugins` do seu servidor
3. **Reinicie** o servidor
4. **Configure** o arquivo `config.yml` conforme necessário
5. **Pronto!** O plugin está funcionando

## ⚙️ Configuração

### Configuração Básica (config.yml)

```yaml
# Configurações do Banco de Dados
database:
  type: "sqlite" # sqlite ou mysql
  host: "localhost"
  port: 3306
  database: "devticket"
  username: "root"
  password: ""

# Configurações de Tickets
tickets:
  max-per-player: 5
  cooldown-seconds: 300
  auto-close-days: 7
  categories:
    - "Suporte Técnico"
    - "Denúncia"
    - "Sugestão"
    - "Bug Report"

# Notificações Discord
notifications:
  discord:
    enabled: false
    webhook-url: "https://discord.com/api/webhooks/..."
```

### Configuração MySQL

Para usar MySQL, altere as configurações do banco:

```yaml
database:
  type: "mysql"
  host: "seu-host-mysql"
  port: 3306
  database: "devticket"
  username: "seu-usuario"
  password: "sua-senha"
  pool-size: 10
```

## 🎮 Comandos

### Comandos para Jogadores
```
/ticket                           - Abrir menu principal
/ticket create <categoria> <título> [descrição] - Criar ticket
/ticket list                      - Ver seus tickets
/ticket view <id>                 - Ver detalhes do ticket
/ticket comment <id> <mensagem>   - Adicionar comentário
```

### Comandos para Staff
```
/ticket list <jogador>            - Ver tickets de um jogador
/ticket assign <id> <staff>       - Atribuir ticket
/ticket close <id> [motivo]       - Fechar ticket
/ticket reopen <id>               - Reabrir ticket
```

### Comandos para Administradores
```
/ticket stats                     - Ver estatísticas
/ticket reload                    - Recarregar configuração
```

## 🔐 Permissões

| Permissão | Descrição | Padrão |
|-----------|-----------|---------|
| `devticket.create` | Criar tickets | `true` |
| `devticket.view.own` | Ver próprios tickets | `true` |
| `devticket.view.all` | Ver todos os tickets | `op` |
| `devticket.manage` | Gerenciar tickets (staff) | `op` |
| `devticket.admin` | Acesso administrativo | `op` |

## 🔧 API para Desenvolvedores

O DevTicket oferece uma API completa para integração com outros plugins:

```java
// Obter instância da API
TicketAPI api = DevTicket.getInstance().getTicketAPI();

// Criar ticket programaticamente
api.createTicket(player, "Título", "Conteúdo", "Categoria", "Prioridade")
   .thenAccept(ticket -> {
       if (ticket != null) {
           // Ticket criado com sucesso
       }
   });

// Obter tickets de um jogador
api.getPlayerTickets(playerUUID)
   .thenAccept(tickets -> {
       // Processar lista de tickets
   });

// Escutar eventos
@EventHandler
public void onTicketCreate(TicketCreateEvent event) {
    Ticket ticket = event.getTicket();
    Player player = event.getPlayer();
    // Processar criação de ticket
}
```

### Eventos Disponíveis
- `TicketCreateEvent` - Quando um ticket é criado
- `TicketCloseEvent` - Quando um ticket é fechado
- `TicketAssignEvent` - Quando um ticket é atribuído
- `TicketCommentEvent` - Quando um comentário é adicionado

## 📊 Recursos Avançados

### Sistema de Estatísticas
- Total de tickets criados
- Tickets por categoria
- Tempo médio de resolução
- Performance da equipe

### Integração Discord
Configure webhooks para receber notificações:
1. Crie um webhook no seu servidor Discord
2. Cole a URL no `config.yml`
3. Ative as notificações desejadas

### Fechamento Automático
Tickets antigos são fechados automaticamente após o período configurado, mantendo o sistema organizado.

## 🛠️ Desenvolvimento

### Estrutura do Projeto
```
DevTicket/
├── src/main/java/me/devplugins/
│   ├── api/                    # API pública
│   ├── commands/               # Comandos
│   ├── config/                 # Configuração
│   ├── database/               # Banco de dados
│   ├── gui/                    # Interface gráfica
│   ├── integrations/           # Integrações externas
│   ├── listeners/              # Event listeners
│   ├── manager/                # Gerenciadores
│   └── model/                  # Modelos de dados
└── src/main/resources/
    ├── config.yml              # Configuração padrão
    └── plugin.yml              # Metadados do plugin
```

### Tecnologias Utilizadas
- **Java 17** - Linguagem principal
- **Spigot API 1.18.2** - API do Minecraft
- **HikariCP** - Pool de conexões
- **SQLite/MySQL** - Banco de dados
- **Gradle** - Build system

## 🤝 Contribuição

Contribuições são bem-vindas! Para contribuir:

1. Fork o projeto
2. Crie uma branch para sua feature (`git checkout -b feature/AmazingFeature`)
3. Commit suas mudanças (`git commit -m 'Add some AmazingFeature'`)
4. Push para a branch (`git push origin feature/AmazingFeature`)
5. Abra um Pull Request

## 📝 Changelog

### v2.0.0
- ✨ Interface gráfica completamente redesenhada
- 🗄️ Sistema de banco de dados (SQLite/MySQL)
- 📋 Categorias e prioridades
- 👥 Sistema de atribuição de tickets
- 🔔 Notificações Discord
- 🛡️ Sistema de cooldown e limites
- 🔧 API completa para desenvolvedores
- 📊 Sistema de estatísticas
- 🎨 Melhorias visuais e de usabilidade

### v1.0.0
- 🎫 Sistema básico de tickets
- 📖 Criação via livro
- 👀 Visualização simples
- ⚡ Funcionalidades essenciais

## 📞 Suporte

- **Discord**: [https://discord.gg/A4F9jtGhFU](https://discord.gg/A4F9jtGhFU)
- **Issues**: Reporte bugs e sugestões nas Issues do GitHub
- **Wiki**: Documentação detalhada na Wiki do projeto

## 📄 Licença

Este projeto está licenciado sob a Licença MIT - veja o arquivo [LICENSE](LICENSE) para detalhes.

## 🙏 Agradecimentos

- Comunidade Spigot/Paper pelo suporte
- Contribuidores do projeto
- Servidores que testaram o plugin
- Feedback da comunidade brasileira de Minecraft

---

**Desenvolvido com ❤️ por DevPlugins**

*DevTicket - Transformando o suporte do seu servidor!*
