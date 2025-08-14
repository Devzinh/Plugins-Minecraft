# DevModt v1.0 - Sistema Profissional de MOTD Dinâmico

Plugin empresarial para Minecraft (Spigot 1.21+) desenvolvido pela **DevPlugins Team**. Sistema completo de gerenciamento de MOTD com recursos avançados, eventos pré-configurados, API pública, métricas de performance e banco de dados integrado.

## 🚀 Funcionalidades Profissionais

### Core Features
- **Rotação Automática Inteligente**: Sistema avançado de rotação com priorização
- **Detecção de Clima Avançada**: Suporte completo a todos os tipos de clima
- **Eventos Especiais Automáticos**: Natal, Halloween, Ano Novo com detecção automática
- **Eventos Pré-Configurados**: 8+ eventos prontos para usar (Gladiador, PvP, Build, etc.)
- **Eventos Customizados**: Sistema completo de criação e gerenciamento
- **Análise de Jogadores**: MOTDs baseados em faixas de jogadores online
- **Sistema de Horários**: Mensagens específicas por período do dia

### Recursos Avançados
- **API Pública**: Integração com outros plugins via API completa
- **Banco de Dados SQLite**: Histórico completo e estatísticas
- **Sistema de Métricas**: Performance e analytics em tempo real
- **Placeholders Avançados**: 20+ placeholders incluindo TPS, CPU, memória
- **Placeholders Customizados**: Registre seus próprios placeholders
- **Verificação de Atualizações**: Sistema automático de update checking
- **Logs Detalhados**: Sistema completo de logging e debugging

### Performance & Segurança
- **Processamento Assíncrono**: Zero impacto na performance do servidor
- **Cache Inteligente**: Sistema de cache para otimização
- **Rate Limiting**: Proteção contra spam de atualizações
- **Validação de Dados**: Validação completa de configurações

## 🎮 Comandos Profissionais

### Comandos Básicos
- `/devmotd reload` - Recarrega configurações
- `/devmotd preview` - Preview do MOTD atual
- `/devmotd info` - Informações do plugin

### Gerenciamento de Eventos
- `/devmotd setevent <nome> [mensagem]` - Ativar evento (pré-config ou custom)
- `/devmotd clearevent` - Remover evento atual
- `/devmotd events` - Listar eventos pré-configurados disponíveis

### Analytics & Métricas
- `/devmotd stats` - Estatísticas de hoje
- `/devmotd metrics` - Métricas de performance
- `/devmotd history [limite]` - Histórico de atualizações

### Placeholders Avançados
- `/devmotd placeholder list` - Listar placeholders customizados
- `/devmotd placeholder add <nome> <valor>` - Adicionar placeholder
- `/devmotd placeholder remove <nome>` - Remover placeholder

### Ferramentas de Desenvolvimento
- `/devmotd test <mensagem>` - Testar processamento de mensagem
- `/devmotd update` - Verificar atualizações
- `/devmotd performance` - Métricas detalhadas de performance
- `/devmotd force` - Forçar atualização imediata do MOTD

**Aliases**: `/dmotd`, `/dynamicmotd`

## 🎮 Eventos Pré-Configurados

O DevModt v2.0 inclui eventos prontos para usar! Basta digitar `/devmotd setevent <nome>`:

### Eventos Disponíveis
- **gladiador** - `⚔️🛡️ GLADIADOR! ⚔️️️🛡️` - Evento de combate PvP
- **pvp** - `⚔️ EVENTO PVP! ⚔️` - Evento de batalhas
- **build** - `🏗️ EVENTO BUILD! 🏗️` - Evento de construção
- **minigames** - `🎮 MINIGAMES! 🎮` - Evento de mini-jogos
- **economia** - `💰 EVENTO ECONOMIA! 💰` - Evento econômico
- **natal** - `🎄 FELIZ NATAL! 🎄` - Evento de Natal (automático 20-26/12)
- **halloween** - `🎃 HALLOWEEN! 🎃` - Evento de Halloween (automático 28/10-01/11)
- **ano_novo** - `🎆 FELIZ ANO NOVO! 🎆` - Evento de Ano Novo (automático 31/12-02/01)

### Como Usar
```bash
# Ativa evento pré-configurado automaticamente
/devmotd setevent gladiador

# Lista todos os eventos disponíveis
/devmotd events

# Ainda funciona para eventos customizados
/devmotd setevent meu_evento Minha mensagem personalizada
```

## Permissões

- `devmotd.admin` - Permite usar todos os comandos (padrão: OP)
- `devmotd.api` - Permite usar a API do DevModt
- `devmotd.stats` - Permite ver estatísticas do DevModt
- `devmotd.update` - Recebe notificações de atualização

## 📊 Placeholders Disponíveis

### Básicos
- `{players_online}` - Jogadores online
- `{max_players}` - Máximo de jogadores
- `{weather}` - Clima atual
- `{event_name}` - Nome do evento ativo
- `{time}` - Hora atual (HH:mm)
- `{date}` - Data atual (dd/MM/yyyy)
- `{full_date}` - Data e hora completa
- `{uptime}` - Tempo de atividade

### Servidor
- `{server_name}` - Nome do servidor
- `{server_version}` - Versão do servidor
- `{bukkit_version}` - Versão do Bukkit
- `{world_count}` - Número de mundos
- `{plugin_count}` - Número de plugins

### Performance
- `{tps}` - TPS atual do servidor
- `{memory_used}` - Memória RAM usada
- `{memory_max}` - Memória RAM máxima
- `{cpu_usage}` - Uso de CPU

### Tempo
- `{day_of_week}` - Dia da semana
- `{month}` - Mês atual
- `{year}` - Ano atual

### Customizados
Registre seus próprios placeholders via comando ou API!

## ⚙️ Configuração Avançada

O arquivo `config.yml` permite configurar:

### Configurações Básicas
- Intervalo de rotação das mensagens
- Mensagens por clima, horário e número de jogadores
- Eventos especiais com datas específicas
- Ativação/desativação de funcionalidades
- Logs detalhados no console

### Configurações de Performance
- Cache inteligente com TTL configurável
- Processamento assíncrono
- Rate limiting para proteção
- Métricas de performance

### Configurações de Prioridade
- Hierarquia configurável de MOTDs
- Resolução de conflitos entre eventos
- Compatibilidade com outros plugins

### Eventos Pré-Configurados
Adicione seus próprios eventos no config.yml:
```yaml
events:
  meu_evento:
    name: "Meu Evento"
    start_date: "01-01"
    end_date: "12-31"
    message: "&d&lMEU EVENTO!\n&7Descrição aqui!"
```

## Instalação

1. Compile o plugin com `./gradlew build`
2. Copie o arquivo `.jar` gerado para a pasta `plugins/` do servidor
3. Reinicie o servidor
4. Configure o arquivo `config.yml` conforme necessário
5. Use `/devmotd reload` para aplicar mudanças

## Desenvolvimento

- **Java**: 21+
- **API**: Spigot 1.21
- **Build**: Gradle

### Estrutura do Projeto

```
src/main/java/me/devplugins/devModt/
├── DevModt.java                    # Classe principal
├── api/
│   ├── DevModtAPI.java            # API pública
│   └── events/
│       └── MOTDUpdateEvent.java   # Eventos da API
├── commands/
│   └── CommandHandler.java       # Gerenciamento de comandos
├── listeners/
│   └── WeatherListener.java      # Eventos de clima
├── managers/
│   ├── ConfigManager.java        # Gerenciamento de configuração
│   ├── DatabaseManager.java      # Banco de dados SQLite
│   ├── EventManager.java         # Gerenciamento de eventos
│   ├── MetricsManager.java       # Sistema de métricas
│   ├── MOTDManager.java           # Lógica principal do MOTD
│   └── PlaceholderManager.java   # Placeholders avançados
└── utils/
    ├── Scheduler.java             # Agendamento de tarefas
    └── UpdateChecker.java         # Verificação de atualizações
```

## 🔧 API para Desenvolvedores

O DevModt v2.0 inclui uma API completa para integração com outros plugins:

### Controle de MOTD
```java
// Forçar atualização do MOTD
DevModtAPI.forceUpdateMOTD();

// Definir evento customizado
DevModtAPI.setCustomEvent("Meu Evento", "&c&lEVENTO ESPECIAL!");

// MOTD temporário (novo!)
DevModtAPI.setTemporaryMOTD("&a&lTEMPORÁRIO!", 300, "MeuPlugin");

// Obter MOTD atual
String motd = DevModtAPI.getCurrentMOTD();

// Preview sem aplicar
String preview = DevModtAPI.getPreviewMOTD();
```

### Placeholders Avançados
```java
// Registrar placeholder customizado
DevModtAPI.registerPlaceholder("meu_placeholder", "Valor");

// Placeholder dinâmico
DevModtAPI.registerPlaceholder("jogadores_vip", () -> {
    return String.valueOf(getVipPlayers().size());
});

// Remover placeholder
DevModtAPI.unregisterPlaceholder("meu_placeholder");
```

### Eventos e Métricas
```java
// Escutar mudanças de MOTD
@EventHandler
public void onMOTDUpdate(MOTDUpdateEvent event) {
    String oldMOTD = event.getOldMOTD();
    String newMOTD = event.getNewMOTD();
    // Sua lógica aqui
}

// Acessar métricas
PerformanceMetrics metrics = DevModtAPI.getPerformanceMetrics();
double avgTime = metrics.getAverageProcessingTime();
```

Veja `API_EXAMPLE.md` para exemplos completos de integração.

## 📈 Métricas e Analytics Profissionais

### Sistema de Banco de Dados
- **SQLite Integrado**: Histórico completo persistente
- **Estatísticas Diárias**: Métricas automáticas por dia
- **Backup Automático**: Dados seguros e recuperáveis

### Monitoramento em Tempo Real
- **Performance Monitoring**: TPS, CPU, memória em tempo real
- **Tempo de Processamento**: Métricas de latência por operação
- **Cache Analytics**: Hit rate e performance do cache
- **API Calls**: Tracking de chamadas da API

### Relatórios Detalhados
- **Comandos Integrados**: `/devmotd stats`, `/devmotd metrics`
- **Histórico Completo**: `/devmotd history` com filtros
- **Exportação**: Dados acessíveis via API
- **Logs Estruturados**: Sistema de logging profissional

## 🏢 Versão Empresarial v2.0

Esta é a versão profissional do DevModt, desenvolvida pela **DevPlugins Team** com:

### Recursos Enterprise
- ✅ **Eventos Pré-Configurados**: 8+ eventos prontos para usar
- ✅ **API Completa**: Integração avançada com outros plugins
- ✅ **Banco de Dados SQLite**: Persistência e analytics
- ✅ **Sistema de Métricas**: Performance monitoring profissional
- ✅ **Cache Inteligente**: Otimização automática de performance
- ✅ **Processamento Assíncrono**: Zero impacto no servidor
- ✅ **Verificação de Atualizações**: Sistema automático
- ✅ **Logs Detalhados**: Sistema de logging estruturado

### Suporte Profissional
- ✅ **Suporte Técnico Prioritário**: Resposta em até 24h
- ✅ **Atualizações Regulares**: Novas funcionalidades mensais
- ✅ **Documentação Completa**: Guias e exemplos detalhados
- ✅ **Compatibilidade Garantida**: Testado em servidores grandes
- ✅ **Customização**: Eventos e configurações personalizadas

## 🚀 Novidades da v2.0

### ✨ Eventos Pré-Configurados
- **8+ eventos prontos**: Gladiador, PvP, Build, MiniGames, Economia e mais
- **Ativação instantânea**: `/devmotd setevent gladiador` ativa automaticamente
- **Tab completion inteligente**: Sugere eventos disponíveis
- **Mensagens personalizadas**: Cada evento com design único

### 🔧 Melhorias Técnicas
- **Performance otimizada**: Cache inteligente e processamento assíncrono
- **API expandida**: Novos métodos para desenvolvedores
- **Banco de dados**: SQLite integrado para persistência
- **Métricas avançadas**: Sistema completo de analytics

### 🎯 Facilidade de Uso
- **Comandos simplificados**: Menos digitação, mais funcionalidade
- **Interface melhorada**: Mensagens mais claras e organizadas
- **Documentação expandida**: Guias completos e exemplos práticos

## 📞 Suporte Profissional

- **Discord**: https://discord.gg/A4F9jtGhFU
- **GitHub**: https://github.com/devplugins/devmodt
- **Documentação**: Wiki completa com exemplos
- **Suporte Prioritário**: Resposta garantida em 24h
- **Comunidade**: Mais de 1000+ servidores usando

## 📋 Changelog v2.0

- ✅ **Eventos Pré-Configurados**: Sistema completo implementado
- ✅ **Performance**: Cache inteligente e processamento assíncrono
- ✅ **API**: Expandida com novos métodos e eventos
- ✅ **Banco de Dados**: SQLite para persistência e analytics
- ✅ **Comandos**: 4 novos comandos adicionados
- ✅ **Placeholders**: 10+ novos placeholders avançados
- ✅ **Logs**: Sistema de logging profissional
- ✅ **Compatibilidade**: Melhor integração com outros plugins

---

**DevModt v2.0** - O Sistema de MOTD Mais Avançado do Minecraft  
Desenvolvido com ❤️ pela **DevPlugins Team**
