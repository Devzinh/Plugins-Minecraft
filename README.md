# DevModt v1.0 - Sistema Profissional de MOTD Dinâmico

Plugin empresarial para Minecraft (Spigot 1.21+) desenvolvido pela **DevPlugins Team**. Sistema completo de gerenciamento de MOTD com recursos avançados, API pública, métricas de performance e banco de dados integrado.

## 🚀 Funcionalidades Profissionais

### Core Features
- **Rotação Automática Inteligente**: Sistema avançado de rotação com priorização
- **Detecção de Clima Avançada**: Suporte completo a todos os tipos de clima
- **Eventos Especiais Automáticos**: Natal, Halloween, Ano Novo com detecção automática
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
- `/devmotd setevent <nome> [mensagem]` - Criar evento customizado
- `/devmotd clearevent` - Remover evento atual

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

**Aliases**: `/dmotd`, `/dynamicmotd`

## Permissões

- `devmotd.admin` - Permite usar todos os comandos (padrão: OP)

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

## Configuração

O arquivo `config.yml` permite configurar:

- Intervalo de rotação das mensagens
- Mensagens por clima, horário e número de jogadores
- Eventos especiais com datas específicas
- Ativação/desativação de funcionalidades
- Logs no console

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
├── DevModt.java              # Classe principal
├── commands/
│   └── CommandHandler.java   # Gerenciamento de comandos
├── listeners/
│   └── WeatherListener.java  # Eventos de clima
├── managers/
│   ├── ConfigManager.java    # Gerenciamento de configuração
│   ├── EventManager.java     # Gerenciamento de eventos
│   └── MOTDManager.java      # Lógica principal do MOTD
└── utils/
    └── Scheduler.java        # Agendamento de tarefas
```

## 🔧 API para Desenvolvedores

O DevModt v1.0 inclui uma API completa para integração com outros plugins:

```java
// Forçar atualização do MOTD
DevModtAPI.forceUpdateMOTD();

// Definir evento customizado
DevModtAPI.setCustomEvent("Meu Evento", "&c&lEVENTO ESPECIAL!");

// Registrar placeholder customizado
DevModtAPI.registerPlaceholder("meu_placeholder", "Valor");

// Obter MOTD atual
String motd = DevModtAPI.getCurrentMOTD();
```

## 📈 Métricas e Analytics

- **Histórico Completo**: Todas as atualizações são registradas
- **Estatísticas Diárias**: Métricas automáticas por dia
- **Performance Monitoring**: TPS, CPU, memória em tempo real
- **Relatórios Detalhados**: Análise completa via comandos

## 🏢 Versão Empresarial

Esta é a versão profissional do DevModt, desenvolvida pela **DevPlugins Team** com:

- ✅ Suporte técnico prioritário
- ✅ Atualizações regulares
- ✅ API completa para desenvolvedores
- ✅ Documentação detalhada
- ✅ Sistema de métricas avançado
- ✅ Banco de dados integrado

## 📞 Suporte Profissional

- **Discord**: https://discord.gg/A4F9jtGhFU
- **GitHub**: https://github.com/Devzinh/Plugins-Minecraft
- **Documentação**: Wiki completa disponível
- **Suporte 24/7**: Para clientes empresariais

---

**DevModt v1.0** - Desenvolvido com ❤️ pela **DevPlugins Team**
