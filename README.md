<!-- README.md | Atualizado em: 15-10-2026 09:19:08(GMT-04:00) -->

# 🧠 Painel de Contexto — ai-control

<img src="https://img.shields.io/badge/Status-Ativo-success?style=flat-square" alt="Status" />
<img src="https://img.shields.io/badge/Semáforo-LIVRE-success?style=flat-square" alt="Semáforo" />
<img src="https://img.shields.io/badge/Ambiente-Integrado-purple?style=flat-square" alt="Ambiente" />
<img src="https://img.shields.io/badge/Sync-GMT--04%3A00-informational?style=flat-square" alt="Sync" />
<img src="https://img.shields.io/badge/Grounding-Ativo-blueviolet?style=flat-square" alt="Grounding" />

> **Vitalia Kit v0.5.0 — Ledger de Memória Persistente e Orquestração Multi-Máquina.**  
> Este repositório armazena o histórico distribuído, aprendizados consolidados e o controle de concorrência das sessões de trabalho do framework Vitalia.

---

## 📡 Topologia de Shards & Sincronização

<div align="center">

```mermaid
flowchart TD
  Cloud(("☁️ Git Remoto / Hub"))
  M_c01fdc4a["💻 ai-control-server-01<br/><i>specs/004-full-stack-realignment</i><br/><code>Integrado</code>"]
  M_c01fdc4a <-->|"15-10-2026 08:24:20(GMT-04:00)"| Cloud
  style M_c01fdc4a stroke:#8250df,stroke-width:2px,fill:#fbefff,color:#8250df
  style Cloud stroke:#1a7f37,stroke-width:2px,fill:#dafbe1,color:#1a7f37
```

</div>

---

## 🖥️ Máquinas e Status Atual

<table>
  <thead>
    <tr>
      <th align="left">Máquina / ID</th>
      <th align="left">Tarefa Atual</th>
      <th align="center">Ambiente</th>
      <th align="center">Status</th>
      <th align="left">Último Sync</th>
      <th align="left">Próximo Passo (P0)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>ai-control-server-01</strong> (<code>c01fdc4a</code>)</td>
      <td>specs/004-full-stack-realignment</td>
      <td align="center"><img src="https://img.shields.io/badge/-Integrado-purple?style=flat-square" alt="Integrado" /></td>
      <td align="center"><span style="color:green;">●</span> Concluído</td>
      <td>15-10-2026 08:24:20(GMT-04:00)</td>
      <td><strong>Testes funcionais de ponta a ponta na interface autenticada e avanço para integração do canal Omnichannel (WhatsApp Baileys / Evolution API).</strong></td>
    </tr>
  </tbody>
</table>

---

## 🎯 Sessão Ativa em Destaque

- **Estação Ativa:** `ai-control-server-01` (`c01fdc4a`)
- **Tarefa em Execução:** specs/004-full-stack-realignment
- **🎯 Próximo Passo Prioritário (P0):** `Testes funcionais de ponta a ponta na interface autenticada e avanço para integração do canal Omnichannel (WhatsApp Baileys / Evolution API).`
- **Última Sincronização:** `15-10-2026 08:24:20(GMT-04:00)`

---

## 📚 Histórico, Decisões & Guard Rails

<details>
<summary><strong>🔍 Clique para expandir o Histórico Completo de Sessões</strong></summary>

<br/>

| Data / Hora | Estação (ID) | Tarefa Executada | Próximo Passo (P0) |
| :--- | :--- | :--- | :--- |
| 15-10-2026 08:24:20(GMT-04:00) | `ai-control-server-01 (c01fdc4a)` | specs/004-full-stack-realignment | `Testes funcionais de ponta a ponta na interface autenticada e avanço para integração do canal Omnichannel (WhatsApp Baileys / Evolution API).` |
| 12-10-2026 13:15:34(GMT-04:00) | `ai-control-server-01 (c01fdc4a)` | specs/002-frontend-seed | `Construção dos formulários no Frontend (Next.js 16) para permitir adicionar e editar os dados da organização, projetos, squads e departamentos.` |
| 09-10-2026 19:58:59(GMT-04:00) | `ai-control-server-01 (c01fdc4a)` | specs/001-core-foundations | `Adequação do core/management/commands/seed_demo.py e criação da primeira versão do frontend para consumo da API.` |
| 08-10-2026 09:45:32(GMT-04:00) | `ai-control-server-01 (c01fdc4a)` | Treinamento Socrático e Sumário Executivo | `Nenhum pendente. A base documental e arquitetural (backend) está concluída e formalmente empacotada. O próximo passo dependerá da definição de um novo Épico ou repasse para a equipe/stakeholders.` |
| 07-10-2026 17:42:23(GMT-04:00) | `ai-control-server-01 (c01fdc4a)` | Refatoração RBAC 4-Tier e Unificação de Banco | `Nenhum pendente. Backend arquiteturalmente estabilizado.` |
| 07-10-2026 17:42:04(GMT-04:00) | `ai-control-server-01 (c01fdc4a)` | Refatoração RBAC 4-Tier e Unificação de Banco | `Nenhum pendente. Backend arquiteturalmente estabilizado.` |
</details>

<details>
<summary><strong>⚖️ Clique para expandir as Decisões Arquiteturais Consolidadas</strong></summary>

<br/>

| Máquina (ID) | Decisão Arquitetural | Impacto / Racional |
| :--- | :--- | :--- |
| `c01fdc4a` | **[46baf5bd]** `PROJETO` Criação de endpoints de busca de usuários (/api/v1/users/search/) e catálogos dinâmicos (/api/v1/workspaces/catalog/...) com auto-geração de siglas e slugs no frontend. | Humaniza completamente a experiência nos modais de alocação e cadastro 4-Tier, impedindo que o operador precise manipular UUIDs ou códigos brutos. |
| `c01fdc4a` | **[78c21edb]** `ARQUITETURA` Otimização anti-N+1 em ActiveWorkspacesView com carregamento em lote de departamentos, projetos e squads via __in e agrupamento em memória com complexidade O(1). | Reduz o volume de consultas de 13+ para exatamente 4 queries SQL sob assertion estrita, eliminando travamento relacional. |
| `c01fdc4a` | **[e038e238]** `ARQUITETURA` Adoção de TanStack Query v5 como fonte única da verdade para Server-State com factory SSR e decomposição do monólito page.tsx em 6 componentes puros de apresentação. | Resolve definitivamente o erro de runtime No QueryClient set, isola re-renderizações e viabiliza reatividade instantânea pós-mutação. |
| `c01fdc4a` | **[68dcb098]** `ARQUITETURA` Segurança condicional do endpoint OpenAPI (drf-spectacular) inspecionando settings.DEBUG em runtime. | Permite que geradores CLI locais funcionem sem autenticação em dev, enquanto blinda a topologia do PaaS Data Vault em produção (OWASP API9:2023). |
| `c01fdc4a` | **[a50b3792]** `ARQUITETURA` Autenticação JWT Stateless com interceptor Axios resiliente (fila assíncrona isRefreshing). | Evita corrida de concorrência em requisições paralelas durante a expiração do token de acesso, mantendo a navegação do usuário contínua. |
| `c01fdc4a` | **[988450cd]** `[ARQUITETURA]` Uso de blocos 'collapsible' (<details>) do Markdown Socrático. | Emula a dinâmica socrática, forçando o desenvolvedor (usuário final) a raciocinar sobre os Post-Mortems de arquitetura antes de visualizar a solução da equipe. |
| `c01fdc4a` | **[3e834ed9]** `[ARQUITETURA]` Armazenamento dos Manuais de Negócios e Treinamento estritamente no repositório Git (Não exposto publicamente). | Evita a exposição acidental em portais estáticos inseguros (MkDocs) de documentos que contêm estratégias de engenharia e regras sensíveis de RBAC do sistema. |
| `c01fdc4a` | **[af47736b]** `[ARCH]` Implementação do RBAC Hierárquico 4-Tier atrelado aos Documentos de RAG, usando slugs de permissão em vez de roles textuais fixas no Middleware. | Registro defasado |
</details>

<details>
<summary><strong>🛡️ Clique para expandir os Guard Rails de Grounding e Domínios</strong></summary>

<br/>

| Arquivo de Regras | Status | Domínios Monitorados | Pendentes de Curadoria HITL |
| :--- | :---: | :--- | :---: |
| `grounding-domains.yaml` (Global) | ✅ Ativo | `llm_models`, `python_packages`, `external_apis`, `security_practices`, `regulations`, `cloud_services`, `scientific_claims` | — |
| `grounding-domains-local.yaml` (Projeto) | ✅ Sincronizado | Domínios locais específicos do workspace | `0 pendências` |

</details>

---

<sub>Painel gerado automaticamente pelo motor de contexto do Vitalia Kit (<code>vitalia_context_engine.py --action consolidate</code>).</sub>
