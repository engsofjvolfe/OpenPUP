> Todos os conteúdos deste projeto, incluindo as mudanças registradas neste arquivo, estão sob Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0). Consulte LICENSE para mais informações.

# Changelog

Todas as mudanças significativas neste projeto serão documentadas neste arquivo e seguem o formato [Keep a Changelog 1.1](https://keepachangelog.com/pt-BR/1.1.0/) e a [Versão Semântica 2.0.0](https://semver.org/lang/pt-BR/).


## [Unreleased]
- Exemplos concretos de uso do protocolo
- Etapa no protocolo a fim de rebater o raciocínio trazido pelo modelo e corrigir seu plano de ação para entrega da resposta

## [1.0.1] - 2025-08-31
### Adicionado
- Declaração explícita de obrigatoriedade nas etapas 5 a 9 do protocolo, com instruções condicionais que visam impedir a progressão da IA caso não sejam concluídas integralmente.
- Inclusão de sinalizadores textuais para controle de fluxo e validação de conformidade antes da entrega.
- Reforço de lógica de parada: se qualquer etapa obrigatória estiver incompleta, a IA deve interromper o processo e registrar o bloqueio na etapa 8.
- Documentação `GUIA_EXPLICATIVO.md`.

## [1.0.0] - 2025-07-14
### Adicionado
- Protocolo Universal de Prompt - OpenPUP
- Documentação `ANALISE.md`, `ARQUITETURA.md`, `CHANGELOG.md`, `LICENSE`, `MANIFESTO.md`, `README.md`, `COMECE_AQUI.md`