# Etapa 0: Modo e Idioma
```
## 0) Modo e Idioma

Humano — preencha os campos YAML abaixo:

modo: FAST        # FAST | THOROUGH  
idioma: PT-BR     # PT-BR | EN | ...  
publico: tecnico  # leigo | intermediario | tecnico  
overflow: resumir_dados_nao_criticos  # se tokens >95%, resuma dados não críticos
contexto_conversa: primeira_vez

IA — faça:  
- Considere estas preferências em toda a resposta.
```

Esta é a porta de entrada para qualquer prompt estruturado com o OpenPUP. Aqui, o humano define parâmetros básicos que orientam toda a conversa com a IA. São escolhas rápidas, mas poderosas — porque elas moldam o *tom*, a *profundidade* e o *público* da resposta.

⚙️ **O que você precisa preencher:**

- **modo:**  
  Indica se quer respostas rápidas e diretas (**FAST**) ou mais detalhadas e minuciosas (**THOROUGH**).  
  Pense assim: quer um resumo ágil ou um mergulho profundo na resposta?

- **idioma:**  
  Escolha o idioma principal da conversa — português, inglês, etc.  
  Isso evita confusão e garante que a IA fale a língua certa para você.

- **publico:**  
  Defina quem vai ler a resposta: leigo, intermediário ou técnico.  
  Isso faz a IA ajustar o vocabulário e a complexidade, para não virar um texto complicado demais nem simples demais.

- **overflow:**  
  O que fazer se a resposta ficar grande demais?  
  Pode escolher, por exemplo, resumir dados menos importantes para caber no limite de texto.

- **contexto_conversa:**  
  Explique se é a primeira vez falando desse assunto ou se já existe um histórico.  
  Assim a IA sabe se deve repetir explicações básicas ou pode pular direto no que importa.

***

🎯 **Por que isso importa?**

Se você não definir esses parâmetros, a IA ficará “no escuro” sobre:

- Quão detalhada deve ser a resposta  
- Para quem está falando — se precisa simplificar ou pode ir direto ao ponto técnico  
- Qual idioma usar para facilitar seu entendimento  
- Como lidar com respostas muito longas  
- Se deve considerar um diálogo já iniciado ou uma conversa nova

Sem essa clareza inicial, o resultado vira um texto genérico, pouco útil e às vezes confuso — o tipo de coisa que a gente tenta evitar com o OpenPUP.

***

⚡ **Na prática:**

Imagine o passo 0 como a configuração inicial do GPS da conversa: você escolhe que rota seguir, para quem entregar a informação e em qual idioma. Tudo pronto para a IA “dirigir” com precisão e não sair pela estrada errada.

---
---

# Etapa 1: Tarefa (o que produzir e em que formato)
```
## 1) Tarefa (o que produzir e em que formato)

Humano — preencha entre os delimitadores abaixo:

### <TASK_BEGIN>
Objetivo: [o que deve ser produzido]  
Formato de saída: [Markdown | tabela | JSON | lista]  
Tamanho-alvo: [ex.: 200–300 palavras]  
### <TASK_END>

Exemplo:  
Objetivo: gerar um resumo sobre [tema]. Formato: Markdown. Tamanho: 250–300 palavras.

IA — faça:  
- Entenda exatamente o objetivo, formato e tamanho-alvo antes de prosseguir.
```

Aqui o humano define claramente o que quer que a IA produza, como quer receber essa informação e qual o tamanho ideal da resposta. É o momento de colocar seu pedido dentro do “envelope” do protocolo para evitar confusões.

⚙️ **O que você precisa preencher:**

- **Objetivo:**  
  Descreva com clareza o que quer que a IA crie ou faça para você.  
  Seja direto e evite frases vagas — quanto mais específico, melhor.

- **Formato de saída:**  
  Escolha o formato da resposta que vai receber, como:  
  - Markdown (texto com formatação leve)  
  - Tabela (informação organizada em linhas e colunas)  
  - JSON (formato estruturado para sistemas)  
  - Lista (itens separados, fáceis de ler)  
  Essa escolha facilita entender a resposta e usar o que receber.

- **Tamanho-alvo:**  
  Defina a extensão da resposta, por exemplo, “200–300 palavras”.  
  Isso ajuda a IA a adequar o conteúdo para nem faltar nem sobrar informação.

Tudo isso deve ser colocado entre as marcas `<TASK_BEGIN>` e `<TASK_END>`, para que a IA saiba exatamente onde está a instrução principal do seu pedido.

***

🎯 **Por que isso importa?**

Sem essa definição clara e organizada da tarefa, a IA pode:

- Entregar respostas vagas ou genéricas que não atendem ao seu objetivo real  
- Enviar conteúdo no formato errado, dificultando seu uso ou leitura  
- Produzir textos muito longos ou muito curtos, que não correspondem à sua necessidade

Essa etapa é o mapa do tesouro para a IA — se o mapa estiver confuso ou incompleto, o “tesouro” pode nunca aparecer.

***

⚡ **Na prática:**

Pense no passo 1 como o rótulo e a embalagem do seu pedido para a IA. Você diz exatamente o que quer, em que “embalagem” quer receber e o tamanho que espera. Assim, a IA entende bem o seu pedido e entrega um resultado que faz sentido para você, sem adivinhações ou desperdício de tempo.

---
---

# Etapa 2: Critérios (priorização do que importa)

```
## 2) Critérios (priorização do que importa)

Humano — liste, atribuindo peso (1.0 obrigatório, 0.5 desejável, –1.0 evitar):

M1: até 300 palavras                 # peso = 1.0  
M2: 3 exemplos práticos              # peso = 1.0  
M3: linguagem clara em PT-BR         # peso = 1.0  
S1: usar bullets quando útil         # peso = 0.5  
A1: jargão sem explicar              # peso = –1.0  
A2: afirmar sem qualificar incerteza # peso = –1.0
D1: deve usar dados de x antes de y

IA — faça:  
- Em caso de conflito, priorize pesos maiores.
```

Nesta etapa, você define quais critérios são mais importantes para a resposta da IA, atribuindo níveis de prioridade (**pesos**) para cada item.  
Isso ajuda a IA a focar exatamente no que importa e evitar o que deve ser evitado.

---

⚙️ O que você precisa preencher

- **Lista de critérios:**  
  Escreva os pontos que você quer que a resposta siga, usando **códigos** e **pesos**.  
  Cada ponto deve indicar se é:  
  - **Obrigatório** → deve ser sempre atendido.  
  - **Desejável** → bom ter, mas não essencial.  
  - **Evitar** → não deve aparecer.  
  - **Regra de dados (D)** → orienta como a IA deve tratar os dados fornecidos.  

---

🎯 O que significam os códigos

- `M (Must)` → deve ser cumprido.  
- `S (Should)` → desejável, mas não obrigatório.  
- `A (Avoid)` → evitar.  
- `D (Data rules)` → regras sobre uso de dados (mais abaixo).  

---

🎯 O que significam os pesos

Os pesos não são contas matemáticas.  
Eles funcionam como **sinais de trânsito**, para mostrar à IA **quem vence em caso de conflito**:

- **1.0 = Vermelho** → prioridade máxima. Não pode ser ignorado.  
- **0.5 = Amarelo** → importante, mas pode ser sacrificado se atrapalhar um vermelho.  
- **–1.0 = Proibido** → deve ser evitado. Só aparece se for impossível atender a um vermelho sem isso.  

👉 Você pode variar os pesos, por exemplo:  
- `0.8` → quase obrigatório, mas não tanto quanto um `1.0`.  
- `–0.3` → preferencialmente evitar, mas tolerável em último caso.  

✅ **Importante:**  
- O **código** (M, S, A, D) classifica o tipo.  
- O **peso** mostra a força relativa.  
- A IA não faz cálculos, mas entende os pesos como sinais claros de prioridade.  

---

⚡ Na prática: Exemplos práticos

- `M1: até 300 palavras # peso = 1.0`  
  → O texto **precisa** ter no máximo 300 palavras.  

- `S1: 3 exemplos práticos # peso = 0.8`  
  → Os exemplos enriquecem, mas se não couber no limite de palavras, o limite vence.  

- `A1: jargão sem explicar # peso = –1.0`  
  → Evite termos técnicos sem explicação. Só pode aparecer se não houver outro jeito de cumprir um critério obrigatório.  

- `D1: usar dados de impacto antes dos dados econômicos # peso = 0.5`  
  → Desejável que os dados de impacto venham primeiro, mas pode mudar a ordem se for necessário.  

---

## 📊 Código `D` — Regras sobre uso de dados

> Você pode usar `M` para qualquer regra sobre dados, mas o código `D` é **recomendado** para dar instruções específicas de como tratar os dados.

O código `D` define **regras de uso dos dados** que você forneceu na Etapa 3 (`<DATA>`).  
Esses dados podem ser: fatos, requisitos, estatísticas ou qualquer informação objetiva que a IA deve usar.

### 🧭 Quando usar o código `D`
Use `D` quando quiser controlar **como os dados devem ser tratados**, e não apenas se devem estar presentes.  

Exemplos:
- `D1: apresentar dados de impacto antes dos dados econômicos`  
- `D2: usar apenas dados do bloco <DATA>`  
- `D3: exibir os dados em tabela, não em texto corrido`  
- `D4: priorizar dados oficiais sobre estimativas`

---

### ⚖️ Como funciona o peso no código `D`

O peso funciona igual aos outros casos:

- `D1: usar dados de X antes de Y` → **1.0** (obrigatório)  
- `D2: apresentar os dados em tabela` → **0.5** (desejável)  
- `D3: evitar dados estimados` → **–1.0** (evitar)  

✅ **Importante:**  
O código `D` **não define se os dados devem estar presentes** (isso é feito nas Etapas 3 e 4).  
Ele apenas define **como os dados devem ser organizados e usados**.

---

### 🔗 Relação com Etapas 3 e 4

- **Etapa 3 (Dados)**: o código `D` ajuda a organizar, filtrar ou priorizar os dados que (se) você fornece no bloco `<DATA>`.  
- **Etapa 4 (Restrições e Condições)**: o código `D` pode reforçar regras como “não usar fontes externas” ou “usar formato JSON”, sem repetir a lógica dessas etapas.

Assim, `D` atua como uma **camada de controle sobre o uso dos dados**, alinhando os critérios da Etapa 2 com as fontes e restrições definidas nas etapas seguintes.

---
---

## Etapa 3: Dados (fonte da verdade)

Nesta etapa, você fornece as informações que a IA deve usar para construir a resposta. Esses dados são a “fonte da verdade” do que será produzido, garantindo que o conteúdo seja preciso e alinhado com o que você deseja.

---

⚙️ O que você precisa preencher

- **Inclua somente informações confiáveis e relevantes:**  
  Coloque aqui dados, requisitos, exemplos ou qualquer conteúdo que a IA deve considerar como base para a resposta.  
  É importante que sejam informações claras, corretas e específicas.

- **Use delimitadores para separar os dados:**  
  Todo esse conteúdo deve ficar entre marcas específicas do protocolo, chamadas de *demarcadores*, para que a IA saiba exatamente o que usar.  
  Isso evita que ela “invente” informações ou traga conteúdo externo não autorizado.

---

🧩 O que são demarcadores?

Demarcadores são sinais visuais claros que indicam onde começam e terminam os dados que devem ser usados.  
O formato padrão é:
```
<DATA> 
[insira aqui dados, requisitos, exemplos, etc] 
</DATA>
```

A IA só deve considerar o que estiver entre essas marcas, **salvo exceções definidas nas regras de restrição**.

🚧 O que são regras de restrição?

As regras de restrição são definidas na Etapa 4 e servem para guiar o comportamento da IA.  
Elas podem incluir:

- Permitir ou negar o uso de fontes externas além dos dados fornecidos  
- Bloquear temas sensíveis ou específicos (ex: aconselhamento médico, menção a marcas)  
- Definir quantas perguntas a IA pode fazer para esclarecer dúvidas  
- Impor formatos obrigatórios (ex: JSON, tabela, lista)

Essas regras tornam a resposta mais segura, adequada e alinhada ao seu contexto.

❗ Importante

- **Não coloque informações fora dos demarcadores**, a menos que as regras de restrição permitam.  
- A IA usará **apenas o que estiver dentro das marcas `<DATA>` como fonte confiável**.  
- Sem demarcadores claros, a IA pode misturar dados verdadeiros com informações externas ou inventadas (“alucinações”).

---

🎯 Por que isso importa?

Sem uma fonte de dados confiável e delimitada, a IA pode gerar respostas imprecisas, confusas ou até inventar informações.  
As regras de restrição garantem que a IA siga limites importantes, tornando a interação mais segura, controlada e apropriada para seu contexto.

---

⚡ Na prática

Pense na Etapa 3 como entregar um **kit de ingredientes selecionados** para um cozinheiro.  
Se você der todo o material certo e nada além disso, o prato que sair da cozinha será o que você esperava — sem surpresas desagradáveis ou ingredientes desconhecidos.

- Os **demarcadores** são o cesto onde você coloca só os ingredientes que podem ser usados.  
- As **regras de restrição** são como dizer ao cozinheiro que ele não pode usar nada da cozinha do vizinho.

Assim, o prato final será exatamente do jeito que você planejou.

---
---

# Etapa 4: Restrições e Condições

```
## 4) Restrições e Condições

Humano — defina usando este padrão:
external_sources: permitido     # permitido | negado  
clarification_policy: max_questions: 3
if_no_response: assume
scope_limits:  
  - não prescrever medicamentos  
  - não citar marcas  
tools_required:  
  - JSON com campos X,Y,Z  
other_conditions:  
  - não usar nada fora de "Dados"

IA — faça:  
- Respeite integralmente essas restrições.
```

Nesta etapa, você define os **limites operacionais** da IA — ou seja, o que ela pode ou não fazer, quais ferramentas ou formatos deve usar, e como deve se comportar diante de dúvidas ou lacunas.  
É o momento de estabelecer regras claras para garantir que a resposta esteja **dentro do escopo desejado**, **segura** e **adequada ao contexto**.

---

⚙️ **O que você precisa preencher:**

- **`external_sources:`**  
  Indica se a IA pode usar informações de fora do que você forneceu.  
  - Use `permitido` se quiser que ela complemente com dados da internet ou fontes externas.  
  - Use `negado` se quiser que ela use **somente** os dados que você colocou no bloco `<DATA>`.

- **`clarification_policy:`**  
  Define como a IA deve agir quando tiver dúvidas ou precisar de mais informações.  
  Você pode controlar isso com dois parâmetros:

  - `max_questions:` limita quantas perguntas a IA pode fazer antes de responder.  
    Exemplo: `max_questions: 2` → a IA pode fazer até duas perguntas de esclarecimento.

  - `if_no_response:` define o que a IA deve fazer se você **não responder** às perguntas dela.  
    Aqui você tem duas opções:
    - Escrever diretamente o que ela deve fazer (ex: `if_no_response: usar formato JSON`)  
    - Usar `assume`, que autoriza a IA a **tomar a melhor decisão possível com base no contexto e nas regras definidas**
    Isso evita que a IA fique travada ou invente soluções aleatórias — ela terá um caminho claro mesmo diante do silêncio.

- **`scope_limits:`**  
  Lista de assuntos ou comportamentos que a IA **não deve abordar**.  
  Serve para impedir que ela entre em temas delicados, proibidos ou fora do seu interesse.  
  Basta escrever cada limite como um item — por exemplo, “não citar marcas” ou “não fazer recomendações médicas”.

- **`tools_required:`**  
  Define **como a resposta deve ser entregue** — em qual formato, estrutura ou ferramenta.  
  Você pode exigir que a IA use JSON, tabela, Markdown, lista com bullets, ou qualquer outro formato específico.  
  Isso garante que o conteúdo venha pronto para o seu uso, sem precisar adaptar depois.

- **`other_conditions:`**  
  Espaço para qualquer outra regra que não se encaixe nas categorias acima.  
  Pode incluir restrições extras, exigências de estilo, proibições específicas ou qualquer detalhe que ajude a moldar a resposta da IA do jeito que você precisa.
  Exemplo:  
  - `evitar linguagem emocional`  
  - `usar apenas exemplos reais`  
  Serve como cláusula extra para reforçar limites ou comportamentos específicos.

---

🎯 **Por que isso importa?**

Sem essas restrições, a IA pode:

- Buscar informações externas que você não quer usar  
- Ultrapassar temas delicados ou proibidos  
- Entregar respostas em formatos inadequados para seu projeto  
- Tomar decisões erradas diante de dúvidas, por falta de política clara

Essas regras funcionam como **barreiras de segurança e precisão**, garantindo que a IA opere dentro dos limites que você definiu.

---

⚡ **Na prática:**

Pense na Etapa 4 como o **manual de conduta** da IA.  
Você diz o que ela pode acessar, como deve se comportar, o que está fora dos limites e como deve entregar o resultado.  
É como colocar placas de “proibido ultrapassar” e “siga por aqui” no caminho da resposta — evitando desvios, riscos e surpresas.

---
---

# ATENÇÃO - A partir da etapa 5 somenta a IA preenche todos os campos (exceto etapa 7) 

# Etapa 5: Análise Prévia (não é a entrega)

```
## 5) Análise Prévia (não é a entrega)

Humano -  estrutura de leitura para IA:
```json
{
  "lacunas": [],
  "assuncoes": [],
  "riscos": []
}

IA — faça:  
- Com base nos itens 1–4, identifique pontos críticos antes de produzir qualquer conteúdo.  
- Apresente sua análise separando claramente os seguintes blocos:

  - **Lacunas** → o que está faltando e pode impedir a entrega correta  
  - **Assunções** → decisões que você (IA) vai tomar por conta própria, se não houver resposta  
  - **Riscos** → pontos que podem gerar erro, ambiguidade ou violar alguma regra

- Use formato escaneável e organizado — como listas com títulos — para facilitar a leitura humana.  

Se houver lacuna crítica que impeça um MUST:  
- Faça até 3 perguntas objetivas e pare.  
- Se não houver resposta, declare as assunções necessárias e siga com a tarefa.
```

Antes de produzir qualquer conteúdo, a IA deve fazer uma **análise técnica inicial** com base nas instruções e dados das Etapas 1 a 4.  
Essa etapa serve para identificar **problemas potenciais**, **decisões que precisam ser tomadas** e **riscos que podem comprometer a qualidade ou segurança da resposta final**.

---

```
{
  "lacunas": [],
  "assuncoes": [],
  "riscos": []
}
```

Esta parte acima representa **a estrutura conceitual que a IA deve ler e interpretar** antes de produzir qualquer conteúdo.  
Ele **não é um modelo de resposta**, mas sim um guia para a IA entender **quais blocos devem compor sua análise textual**.

⚙️ **O que a IA deve fazer:**

- Examinar todos os parâmetros definidos nas etapas anteriores (tarefa, critérios, dados e restrições)
- Identificar e listar:
  - **Lacunas** → informações que estão faltando e podem impedir o cumprimento da tarefa
  - **Assunções** → decisões que a IA terá que tomar por conta própria, por falta de instrução explícita
  - **Riscos** → pontos que podem gerar ambiguidade, erro ou violar alguma regra

- Se houver uma **lacuna crítica** que impeça o cumprimento de um critério obrigatório (`MUST`):
  - A IA pode fazer até **3 perguntas objetivas** para tentar esclarecer
  - Se não houver resposta, ela deve **declarar as assunções necessárias** e seguir com a tarefa

---

📦 **Formato da resposta: estrutura organizada por tópicos**

A análise da IA deve ser apresentada de forma clara e separada em três partes principais:

- **Lacunas** → o que está faltando e pode impedir a entrega correta  
- **Assunções** → decisões que a IA vai tomar por conta própria, se você não responder  
- **Riscos** → pontos que podem gerar erro, ambiguidade ou violar alguma regra

Essas três seções funcionam como uma **lista de verificação**, permitindo que você veja rapidamente:

- O que precisa ser ajustado  
- O que será presumido pela IA  
- Onde pode haver problemas futuros

Esse formato não é só uma exigência técnica — é uma forma de garantir que **você tenha controle total sobre o que está acontecendo**, antes que a IA siga para a entrega final.

---

🎯 **Por que isso importa?**

Sem essa análise prévia, a IA pode:

- Produzir uma resposta incompleta ou errada por falta de dados  
- Tomar decisões arbitrárias sem informar o usuário  
- Ignorar riscos que poderiam ser evitados com um simples ajuste

A Etapa 5 funciona como uma **checagem de segurança e alinhamento antes da entrega** — garantindo que a IA não siga em frente sem estar realmente preparada.

---

⚡ **Na prática:**

Pense na Etapa 5 como o momento em que a IA **revisa o plano antes de executar**.  
Ela verifica se tem tudo que precisa, aponta o que está faltando, e diz quais decisões vai tomar se você não responder.  
Tudo isso de forma organizada, transparente e padronizada — para que você tenha controle total antes de seguir para a entrega final.

---
---

# Etapa 6: Plano de Execução (antes de escrever)

```
## 6) Plano de Execução (antes de escrever)

IA — faça:  
- Apresente um plano estruturado com 1 linha por passo, em formato de tabela com 3 colunas:

  | passo | acao | meta |  
1 | Introdução | contextualizar público | ... |
2 | ... | ... | ... |

- Explique como atenderá MUSTs, SHOULDs e evitará AVOIDs.  
- Estime o tamanho final.

Finalize com a marca: 
<<READY_EXEC>>
```
Antes de começar a redigir a resposta final, a IA deve apresentar um **plano claro e estruturado** de como pretende construir o conteúdo.  
Essa etapa funciona como um **roteiro de produção**, permitindo que o humano veja o caminho que será seguido e faça ajustes antes da execução.

---

📦 **O que a IA deve entregar:**

- Um plano com **uma linha por passo**, organizado em três colunas:
  - **passo** → número sequencial (1, 2, 3...)  
  - **acao** → o que será feito em cada etapa (ex: “apresentar introdução”, “listar exemplos”)  
  - **meta** → o objetivo de cada ação (ex: “contextualizar público”, “ilustrar conceito”)

- Uma explicação breve de como a IA vai:
  - Cumprir os critérios obrigatórios (`MUST`)  
  - Tentar atender os desejáveis (`SHOULD`)  
  - Evitar os elementos proibidos (`AVOID`)

- Uma **estimativa do tamanho final da resposta**, com base no que foi definido na Etapa 1

- Ao final do plano, a IA deve escrever exatamente:  
  `<<READY_EXEC>>`  
  Isso sinaliza que o plano está completo e pronto para ser aprovado ou executado.

---

🎯 **Por que isso importa?**

Sem um plano claro, a IA pode:

- Pular etapas importantes ou incluir conteúdo fora do escopo  
- Ignorar critérios definidos ou misturar prioridades  
- Produzir uma resposta desalinhada com o que o humano espera

O plano de execução permite que o humano **avalie a estratégia antes da escrita**, garantindo que tudo esteja no caminho certo.

---

⚡ **Na prática:**

Pense na Etapa 6 como o **roteiro de um vídeo ou a planta de uma construção**.  
Você vê cada passo antes de começar, entende o propósito de cada parte, e pode corrigir o plano se algo estiver fora do esperado.  
Com isso, a entrega final será mais precisa, eficiente e alinhada com o que você realmente precisa.

---
---

# Etapa 7: Auto-checagem (antes de enviar)

```
## 7) Auto-checagem (antes de enviar)

IA — faça (marque em Markdown):

- [ ] Cumpriu todos os MUST  
- [ ] SHOULD atendidos quando possível  
- [ ] Nenhum AVOID violado  
- [ ] Tamanho e formato conforme Tarefa  
- [ ] Uso exclusivo dos Dados  
- [ ] Incertezas qualificadas
- [ ] Demais critérios definidos por você
```

Antes de entregar a resposta final, a IA deve realizar uma **autoavaliação rigorosa**, marcando cada item da lista acima.

---

📌 **Atenção especial ao último item:**

> “Demais critérios definidos por você”

Esse campo é **personalizável pelo humano**.  
Ou seja, o usuário pode definir critérios adicionais (ex: tom emocional, estilo de linguagem, presença de fontes, etc.)  
A IA deve então **reconhecer esses critérios e incluí-los na checagem**, marcando se foram atendidos ou não.

Exemplo:

Se o humano disser:  
> “Quero que o texto tenha tom inspirador e cite ao menos uma fonte confiável”

A IA deve incluir na checagem:

- [ ] Tom inspirador mantido  
- [ ] Fonte confiável incluída

---

🎯 **Por que isso importa?**

A auto-checagem evita erros por distração ou pressa.  
Ela força a IA a **revisar conscientemente** sua entrega, garantindo que tudo esteja alinhado com o briefing.

---

⚡ **Na prática:**

Pense na Etapa 7 como o **checklist de embarque antes do voo**.  
Se algo estiver fora do padrão, a IA deve corrigir antes de “decolar” com a entrega final.

---
---

# Etapa 8: Regra de Parada

IA — faça:  
- Antes de entregar qualquer conteúdo, verifique se há impedimentos críticos.  
- Se houver, pare e explique o bloqueio com clareza.  
- Proponha solução segura ou solicite dados adicionais.

```
Esta etapa é o freio de emergência do protocolo.  
Ela entra em ação quando a IA percebe que **não pode seguir com a entrega** por falta de dados, risco de erro ou violação de regra.

Em vez de “chutar” ou inventar, a IA deve parar, explicar o motivo e propor uma saída segura.  
É aqui que garantimos que o conteúdo gerado *não seja especulativo, nem fora de escopo*.
```

📦 **O que a IA deve entregar:**

- **bloqueado:**  
  Indica se a entrega está impedida.  
  Se for `true`, a IA deve parar e justificar. Se for `false`, ela pode seguir normalmente.

- **motivo:**  
  Explicação objetiva do porquê a entrega está bloqueada.  
  Pode ser falta de dados, ambiguidade, conflito com regras, etc.

- **proposta:**  
  Sugestão prática para resolver o bloqueio.  
  Pode ser pedir dados adicionais, fazer perguntas ou oferecer uma versão parcial segura.

***

🎯 **Por que isso importa?**

Sem essa etapa, a IA pode tentar entregar algo incompleto, errado ou até perigoso.  
A Regra de Parada protege a qualidade da resposta e evita que o protocolo siga por caminhos incertos.

Ela também mostra que a IA está “pensando antes de falar” — o que aumenta a confiança no conteúdo gerado.

***

⚡ **Na prática:**

Pense na Etapa 9 como o botão de *pausa consciente*.  
Se a IA não tiver o que precisa, ela não improvisa — ela para, explica e propõe.  
É como um bom profissional que diz: “Não posso seguir sem isso — aqui está o que falta e como podemos resolver.”

---
---

# Etapa 8: Entrega (somente após <<READY_EXEC>>, e checklist realizado)

```
## 8) Entrega (somente após <<READY_EXEC>>)

IA — faça:  
- Produza a saída conforme:  
  - O formato definido na Tarefa  
  - Os dados delimitados em <DATA>  
  - Os critérios e restrições definidos antes

Respeite o esquema indicado anteriormente.
Depois que o plano de execução for validado, a IA pode finalmente **escrever a resposta final**.
```
---

📦 **O que a IA deve entregar:**

- A saída completa, conforme:
  - O **formato definido na Tarefa** (ex: artigo, email, roteiro, lista, tabela, etc.)
  - Os **dados delimitados em <DATA>**, se houver
  - Os **critérios e restrições** definidos nas etapas anteriores (MUST, SHOULD, AVOID)

- A IA deve seguir **exatamente o plano aprovado na Etapa 6**, sem improvisar ou alterar a estrutura sem autorização.

---

🚫 **O que a IA não deve fazer:**

- Não pode escrever a resposta antes do `<<READY_EXEC>>`  
- Não pode mudar o formato, tom ou estrutura sem pedir aprovação  
- Não pode incluir conteúdo fora do escopo definido

---

🎯 **Por que isso importa?**

A Etapa 8 é o momento de **execução precisa**, sem desvios.  
A IA já tem tudo que precisa: briefing, critérios, estrutura, plano.  
Agora é só **entregar com excelência**, respeitando cada detalhe acordado.

---

⚡ **Na prática:**

Pense na Etapa 8 como a **fase de produção final**.  
O roteiro já foi aprovado, os critérios estão claros — agora é só executar com fidelidade e qualidade.

> Este projeto é licenciado sob:
- **Documentação**: [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)
- **Implementações em software**: [AGPL-3.0](https://www.gnu.org/licenses/agpl-3.0.html)
