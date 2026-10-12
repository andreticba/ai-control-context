<!-- DECISIONS.md | Atualizado em: 12-10-2026 14:06:24(GMT-04:00) -->
# 🏛️ Decisões de Arquitetura e Governança Consolidadas (ADRs)

**Data/Hora de Geração:** `12-10-2026 14:06:24(GMT-04:00)` | **Fuso Horário:** America/Cuiaba `(GMT-04:00)`

| ID | Categoria | Decisão | Racional | Máquina | Data |
|---|---|---|---|---|---|
| `af47736b` | `[ARCH]` | Implementação do RBAC Hierárquico 4-Tier atrelado aos Documentos de RAG, usando slugs de permissão em vez de roles textuais fixas no Middleware. | Registro defasado | `c01fdc4a` | 07-10-2026 17:42:23(GMT-04:00) |
| `3e834ed9` | `[ARQUITETURA]` | Armazenamento dos Manuais de Negócios e Treinamento estritamente no repositório Git (Não exposto publicamente). | Evita a exposição acidental em portais estáticos inseguros (MkDocs) de documentos que contêm estratégias de engenharia e regras sensíveis de RBAC do sistema. | `c01fdc4a` | 08-10-2026 09:45:32(GMT-04:00) |
| `988450cd` | `[ARQUITETURA]` | Uso de blocos 'collapsible' (<details>) do Markdown Socrático. | Emula a dinâmica socrática, forçando o desenvolvedor (usuário final) a raciocinar sobre os Post-Mortems de arquitetura antes de visualizar a solução da equipe. | `c01fdc4a` | 08-10-2026 09:45:32(GMT-04:00) |
| `a50b3792` | `ARQUITETURA` | Autenticação JWT Stateless com interceptor Axios resiliente (fila assíncrona isRefreshing). | Evita corrida de concorrência em requisições paralelas durante a expiração do token de acesso, mantendo a navegação do usuário contínua. | `c01fdc4a` | 12-10-2026 13:15:34(GMT-04:00) |
| `68dcb098` | `ARQUITETURA` | Segurança condicional do endpoint OpenAPI (drf-spectacular) inspecionando settings.DEBUG em runtime. | Permite que geradores CLI locais funcionem sem autenticação em dev, enquanto blinda a topologia do PaaS Data Vault em produção (OWASP API9:2023). | `c01fdc4a` | 12-10-2026 13:15:34(GMT-04:00) |
