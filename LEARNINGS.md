<!-- LEARNINGS.md | Atualizado em: 31-10-2026 08:53:45(GMT-04:00) -->
# 💡 Aprendizados Técnicos e Lições Aprendidas Consolidadas

**Data/Hora de Geração:** `31-10-2026 08:53:45(GMT-04:00)` | **Fuso Horário:** America/Cuiaba `(GMT-04:00)`

## [PROJETO]
- **Aprendizado:** 
  - **Racional:** Registro defasado
  - **Origem:** `ai-control-server-01` | **Data:** 07-10-2026 17:42:23(GMT-04:00)
- **Aprendizado:** 
  - **Racional:** Registro defasado
  - **Origem:** `ai-control-server-01` | **Data:** 07-10-2026 17:42:23(GMT-04:00)
- **Aprendizado:** Demonstramos um caminho replicável para anonimizar e traduzir problemas técnicos complexos (Post-Mortems com vazamento de código/PII) para material executivo focado em segurança de dados e material educacional gamificado, honrando a Constituição.
  - **Racional:** Resguarda as restrições SC-001 (Sigilo e Segurança) e SC-002 sem sacrificar o treinamento e o acompanhamento de executivos.
  - **Origem:** `ai-control-server-01` | **Data:** 08-10-2026 09:45:32(GMT-04:00)

## [KIT]
- **Aprendizado:** Decisões técnicas como uso de padrões de formatação (ex: tags <details> do Markdown) exigem URLs oficiais (ex: GitHub Docs) no plan.md para passar no Grounding Protocol do SDDJudge. A resiliência do Juiz com fallback local (Ollama) foi comprovada na prática hoje.
  - **Racional:** Evitar o bloqueio do SDDJudge e confirmar tolerância a falhas na API do Gemini.
  - **Origem:** `ai-control-server-01` | **Data:** 08-10-2026 09:45:32(GMT-04:00)

## PROJETO
- **Aprendizado:** [PROJETO] Migração de Models para novos Bounded Contexts exige auditoria manual proativa no admin.py e arquivos secundários (como signals e inlines), já que erros (admin.E108) só quebram o app no momento do boot.
  - **Racional:** Evitar crashes silenciosos em produção e garantir integridade da interface administrativa.
  - **Origem:** `ai-control-server-01` | **Data:** 09-10-2026 19:58:59(GMT-04:00)
- **Aprendizado:** [PROJETO] O uso de network_mode: "host" na Evolution API resolve a fricção no desenvolvimento híbrido, contornando a falha nativa do Docker de enviar webhooks para o servidor local rodando no Host.
  - **Racional:** Garante estabilidade da comunicação Evolution <-> Django no ambiente de desenvolvimento de Engenheiros.
  - **Origem:** `ai-control-server-01` | **Data:** 09-10-2026 19:58:59(GMT-04:00)
- **Aprendizado:** [PROJETO] Compatibilidade DRF 3.16 x Django 6.1: O Django 6.1 removeu cc_delim_re de django.utils.cache, tornando obrigatório o uso de djangorestframework~=3.18.3 em Python 3.14.
  - **Racional:** Evita ImportError durante a inicialização e execução de testes com o Django 6.1.
  - **Origem:** `ai-control-server-01` | **Data:** 12-10-2026 13:15:34(GMT-04:00)
- **Aprendizado:** [PROJETO] Ordem de Limpeza com Soft FKs e Models Protegidos: Modelos com FK protegida (Conversation.contact) exigem a remoção explícita de Message e Conversation antes da deleção de Contact para evitar ProtectedError na flag --flush.
  - **Racional:** Garante a idempotência e execução sem erros do comando seed_demo --flush.
  - **Origem:** `ai-control-server-01` | **Data:** 12-10-2026 13:15:34(GMT-04:00)
- **Aprendizado:** [PROJETO] Restrição Matricial de Nível de Cargo em BaseMembership: O model valida estritamente job_title.level == SCOPE, impedindo a vinculação de cargos de nível SQUAD diretamente em ProjectMembership.
  - **Racional:** Garante integridade e separação estrita da hierarquia organizacional 4-Tier sem violação das validações do modelo.
  - **Origem:** `ai-control-server-01` | **Data:** 12-10-2026 13:15:34(GMT-04:00)
- **Aprendizado:** [PROJETO] Em React 19 / Next.js 16 com SSR e Turbopack, a inicialização do TanStack Query exige uma factory singleton (isServer vs browserQueryClient) para prevenir vazamento de estado entre tenants no servidor e recriações indevidas no cliente.
  - **Racional:** Garante estabilidade no ciclo de vida do QueryClient durante hidratação e evita concorrência multi-tenant no lado do servidor.
  - **Origem:** `ai-control-server-01` | **Data:** 15-10-2026 08:24:20(GMT-04:00)
- **Aprendizado:** [PROJETO] Formulários operacionais que expõem IDs numéricos ou UUIDs quebram a usabilidade; o padrão ideal é fornecer endpoints de catálogo e busca contextual (/users/search/, /catalog/roles/, /catalog/job-titles/) com preenchimento assistido de slugs e siglas.
  - **Racional:** Elimina a barreira de entrada e erros de digitação do usuário final, transferindo a resolução de IDs e UUIDs para a camada de serviço/API.
  - **Origem:** `ai-control-server-01` | **Data:** 15-10-2026 08:24:20(GMT-04:00)
- **Aprendizado:** [PROJETO] Em interfaces de mensageria em tempo real, marcar mensagens como lidas instantaneamente sem checar o foco da janela apaga notificações despercebidas pelo operador; um delay perceptivo (1.5s) somado à verificação de foco garante assimilação da mensagem.
  - **Racional:** Evita perda de visibilidade operacional quando novas mensagens chegam em conversas abertas enquanto o operador está trabalhando em outra janela.
  - **Origem:** `ai-control-server-01` | **Data:** 30-10-2026 18:20:05(GMT-04:00)
- **Aprendizado:** [PROJETO] No ecossistema Django/Pytest, a coexistência de um arquivo 'app/tests.py' com um pacote de testes 'app/tests/' provoca colisão fatal 'import file mismatch' durante a coleta global de testes.
  - **Racional:** Garante que o comando global pytest execute a suíte completa de testes (130 testes) de forma atômica e unificada sem interrupções.
  - **Origem:** `ai-control-server-01` | **Data:** 31-10-2026 08:52:10(GMT-04:00)

## KIT
- **Aprendizado:** [KIT] Preservação de Padrão de Cabeçalho em Projetos Assistidos: Em repositórios com identidade própria, os carimbos devem manter estritamente a convenção do projeto (# NOME_DO_ARQUIVO | AI-Control v0.0.1 | DATA_HORA (GMT-04:00)), sobrepondo tags genéricas do kit.
  - **Racional:** Mantém a coerência da governança documental local em conformidade com as diretrizes do usuário.
  - **Origem:** `ai-control-server-01` | **Data:** 12-10-2026 13:15:34(GMT-04:00)
- **Aprendizado:** [KIT] Em bancos relacionais onde papéis e sementes já foram injetados por migrações estruturais, fixtures de teste de integração devem obrigatoriamente utilizar get_or_create(..., defaults={...}) para evitar falhas espúrias de unicidade (UniqueViolation).
  - **Racional:** Evita falhas falsas-positivas na suíte de testes do pytest ao rodar contra schemas já inicializados.
  - **Origem:** `ai-control-server-01` | **Data:** 15-10-2026 08:24:20(GMT-04:00)
- **Aprendizado:** [KIT] Em testes assíncronos do Django Channels com Pytest, mocks de Channel Layer (group_send) devem ser instanciados com AsyncMock() em vez de MagicMock() para compatibilidade estrita com corrotinas Python 3.14.
  - **Racional:** Previne exceções TypeError: 'MagicMock' object can't be awaited em cenários de despacho de mensagens WebSockets assíncronas.
  - **Origem:** `ai-control-server-01` | **Data:** 30-10-2026 18:20:05(GMT-04:00)
- **Aprendizado:** [KIT] No Next.js 16 (16.4.2), o comando 'next lint' foi removido do core CLI do framework e passa a interpretar o termo 'lint' como argumento de diretório; scripts de lint no package.json devem adotar 'tsc --noEmit' ou chamada explícita ao 'eslint'.
  - **Racional:** Evita falhas de build e erro 'Invalid project directory provided: .../frontend/lint' em esteiras de CI/CD automatizadas.
  - **Origem:** `ai-control-server-01` | **Data:** 31-10-2026 08:52:10(GMT-04:00)
