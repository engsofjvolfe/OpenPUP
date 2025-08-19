# Quick Start OpenPUP

Este é um exemplo funcional do protocolo.  
A diferença para um prompt comum é simples: em vez de jogar uma pergunta solta (“explique tal coisa”), aqui você organiza **o que quer**, **como quer** e **o que deve ser evitado**.  

O resultado? A IA entrega uma resposta **mais clara, estruturada e útil** do que faria com um texto corrido. É útil especialmente para tarefas complexas.

## Como usar:  
1. Copie o prompt abaixo.  
2. Troque `[TEMA]`(presentes na etapa 1 e 3) pelo assunto que você quiser (ex.: “blockchain”, “buracos negros”, “juros compostos”...).  
3. Cole no ChatGPT (ou outra IA generativa) e compare com a resposta que teria se tivesse perguntado apenas “Explique TEMA”.  

A grande diferença? Transparência total. Antes de dar a resposta final, a IA vai te mostrar exatamente como ela planejou construí-la. Você não recebe apenas uma resposta, você vê o raciocínio por trás dela. Isso te dá controle para validar a lógica antes mesmo da entrega final. O resultado é uma explicação clara, com analogias práticas e zero jargão, exatamente como se pede nesse prompt abaixo. Este é um template inicial. Todos os campos podem ser adaptados, mas use-o primeiro; conforme a instrução dada acima, para sentir o poder de comandar a IA.

```
<!-- INÍCIO DO PROMPT OPENPUP - QUICK START FUNCIONAL -->
## 0) Modo e Idioma
modo: THOROUGH
idioma: PT-BR
publico: intermediario
contexto_conversa: primeira_vez

## 1) Tarefa (o que produzir e em que formato)
### <TASK_BEGIN>
Objetivo: Explicar de forma clara e acessível o conceito de "[TEMA]".
Formato de saída: Markdown
Tamanho-alvo: 200-300 palavras
### <TASK_END>

## 2) Critérios (priorização do que importa)
M1: Usar uma analogia do mundo real para ilustrar o conceito # peso = 1.0
M2: Linguagem clara e acessível para não-especialistas # peso = 1.0
A1: Jargão técnico sem explicação # peso = -1.0

## 3) Dados (fonte da verdade)
<DATA>
O tópico a ser explicado é: [TEMA]
</DATA>

## 4) Restrições e Condições
external_sources: permitido
clarification_policy: max_questions: 0
if_no_response: assume
scope_limits:
  - não usar tom excessivamente técnico

## 5) Análise Prévia (não é a entrega)
IA — faça: 
Antes de escrever, analise brevemente se as instruções são claras e se você tem tudo que precisa para gerar uma resposta que atenda aos critérios M1 e M2. Se estiver claro, mencione que está claro o que foi pedido, explicitamente, e prossiga diretamente para criar um plano de execução.

## 6) Plano de Execução (antes de escrever)
IA — faça:
Apresente um plano muito breve, em formato de lista, de como você estruturará a resposta para atender aos MUSTs (ex.: "1. Introduzir o conceito. 2. Apresentar a analogia. 3. Explicar com base na analogia.").

## 7) Entrega (somente após o plano)
IA — faça:
Agora, produza a explicação final conforme definido na Tarefa, seguindo fielmente o plano que você elaborou e atendendo a todos os critérios obrigatórios (M1, M2) e evitando os proibidos (A1).
<!-- FIM DO PROMPT -->
```

> Este documento faz parte do projeto OpenPUP, licenciado sob Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0). Para detalhes completos, consulte o arquivo LICENSE.