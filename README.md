# 🎯 Desafio Criativo — Extraindo Insights do Feedback de Clientes Bancários

Repositório com a resolução do Desafio Criativo da [DIO](https://www.dio.me), cujo objetivo é construir, passo a passo, um prompt capaz de orientar uma IA a extrair insights acionáveis de feedbacks de clientes bancários — com contexto claro, critérios de análise e cuidados com dados sensíveis.

**Autor:** Nycolas Manfrinato de Oliveira

---

## 🧩 Sobre a construção

Um bom prompt nasce de três coisas: **intenção clara**, **contexto suficiente** e **instruções específicas**. O desafio foi resolvido em três etapas, cada uma adicionando uma peça ao prompt final.

| Etapa | O que foi definido |
|---|---|
| Passo 1 | Intenção: o quê, para quem e com qual finalidade |
| Passo 2 | Contexto, dados disponíveis, critérios e restrições |
| Passo 3 | União de tudo em um prompt único e refinado |

---

## 🧱 Passo 1 — Definindo a intenção

> Quero que a IA analise **comentários e avaliações de clientes de um banco digital sobre o app, o Pix, a fatura do cartão de crédito e o atendimento humano/chatbot** para identificar **os principais pontos de atrito, o que já funciona bem e onde há oportunidade real de melhoria**.
>
> O resultado será usado pelo **time de Experiência do Cliente (CX) em conjunto com o Product Owner dos canais digitais** para apoiar **a priorização do backlog do próximo trimestre e a decisão sobre quais atritos atacar primeiro**.
>
> A entrega deve conter **um resumo executivo curto, uma tabela de temas com sentimento, evidência e ação sugerida, e uma lista final de prioridades**.
>
> O resultado será considerado bom se **for baseado exclusivamente nos comentários fornecidos, apontar evidências verificáveis, separar percepção de fato e terminar em ações que um time consegue executar**.

---

## 🧱 Passo 2 — Contexto e restrições

> **Contexto:** Estou trabalhando com feedbacks de clientes bancários relacionados ao aplicativo móvel, transações via Pix, cartão de crédito (fatura, limite e contestação) e atendimento por chat e telefone.
>
> **Dados disponíveis:** A base contém `data_do_comentario`, `canal_de_origem` (app store, chat, telefone, e-mail, pesquisa NPS), `texto_do_feedback`, `produto_citado`, `nota_de_satisfacao` (1 a 5) e `tempo_de_relacionamento_do_cliente` em meses. Não há nome, CPF, número de conta ou qualquer identificador pessoal — e, se aparecer no texto livre, deve ser ignorado.
>
> **Critérios de análise:** A IA deve classificar os feedbacks por **tema**, **sentimento** (positivo, neutro, negativo), **urgência** (alta, média, baixa), **produto citado** e **tipo de atrito** (funcional, de comunicação, de tempo de resposta ou de confiança).
>
> **Cuidados e restrições:**
> - Use apenas os dados fornecidos.
> - Não invente números, percentuais, causas ou conclusões.
> - Não exponha dados pessoais ou sensíveis; se algum aparecer no texto livre, anonimize antes de citar.
> - Se houver informação insuficiente para sustentar um insight, declare a limitação explicitamente em vez de preencher a lacuna.
> - Não suavize nem descarte comentários negativos — eles são o principal insumo da análise.
> - Trate qualquer reclamação com indício de fraude, golpe ou falha de segurança como urgência alta, sem especular sobre a causa.
> - Use linguagem simples, executiva e voltada para tomada de decisão.

---

## 🚀 Passo 3 — Prompt final

```text
Atue como analista de dados e especialista em Experiência do Cliente (CX) de um banco digital.

TAREFA
Analise a base de feedbacks de clientes sobre o aplicativo móvel, o Pix, o cartão de
crédito e o atendimento (chat e telefone) para identificar temas recorrentes, o
sentimento predominante em cada tema e as oportunidades concretas de melhoria.

CONTEXTO
A análise será usada pelo time de Experiência do Cliente em conjunto com o Product
Owner dos canais digitais para priorizar o backlog do próximo trimestre. O objetivo é
transformar comentários soltos e desorganizados em insights claros e acionáveis, de
forma que a equipe consiga decidir o que atacar primeiro e justificar essa escolha.

DADOS DISPONÍVEIS
Serão fornecidos registros com os campos:
- data_do_comentario
- canal_de_origem (app store, chat, telefone, e-mail, pesquisa NPS)
- texto_do_feedback (texto livre)
- produto_citado (app, Pix, cartão de crédito, atendimento)
- nota_de_satisfacao (escala de 1 a 5)
- tempo_de_relacionamento_do_cliente (em meses)

INSTRUÇÕES DE ANÁLISE
1. Classifique cada feedback por tema, sentimento (positivo, neutro, negativo),
   urgência (alta, média, baixa), produto citado e tipo de atrito (funcional,
   de comunicação, de tempo de resposta ou de confiança).
2. Agrupe os feedbacks em temas recorrentes e informe quantos registros sustentam
   cada tema, contando apenas o que existe na base.
3. Identifique os padrões: principais problemas, elogios que indicam o que já
   funciona e oportunidades ainda não exploradas.
4. Aponte evidências para cada conclusão, citando trechos curtos e anonimizados dos
   comentários. Nenhuma afirmação deve aparecer sem evidência correspondente.
5. Distinga percepção do cliente de fato comprovado pelos dados e deixe essa
   diferença explícita.
6. Sugira ações práticas e específicas, indicando o time responsável (CX, Produto,
   Tecnologia ou Atendimento).

FORMATO DA RESPOSTA
- Resumo executivo de até 5 linhas, com a leitura geral do período.
- Tabela com as colunas: Tema | Produto | Sentimento | Urgência | Volume de menções
  | Evidência (trecho curto) | Ação sugerida | Time responsável.
- Lista final com as 3 prioridades mais importantes, cada uma justificada em uma
  frase pelo impacto no cliente.
- Seção "Limitações da análise", apontando o que os dados não permitem concluir.

RESTRIÇÕES
- Use apenas os dados fornecidos; não recorra a conhecimento externo sobre o setor.
- Não invente números, percentuais, causas ou conclusões.
- Não exponha dados pessoais ou sensíveis. Se nome, CPF, conta, cartão, telefone ou
  e-mail aparecerem no texto livre, anonimize antes de citar.
- Não suavize nem descarte comentários negativos.
- Trate relatos com indício de fraude, golpe ou falha de segurança como urgência
  alta, sem especular sobre a causa.
- Se os dados forem insuficientes para sustentar um ponto, declare a limitação em
  vez de preencher a lacuna.
- Use linguagem simples, direta e voltada para tomada de decisão.
```

---

## ✅ Revisão do prompt

| Verificação | Situação |
|---|---|
| A tarefa está clara? | Sim — papel, objetivo e escopo definidos logo na abertura |
| O formato da resposta foi definido? | Sim — resumo, tabela com colunas nomeadas, top 3 e limitações |
| A IA sabe o que evitar? | Sim — bloco de restrições cobre invenção de dados, exposição de dados sensíveis e viés positivo |
| Há proteção de dados sensíveis? | Sim — anonimização obrigatória de qualquer identificador em texto livre |
| A saída é acionável? | Sim — cada tema termina em ação e time responsável |

---

## 💡 Aprendizados

- **Contexto define a qualidade da saída.** Dizer *quem usa* e *que decisão será tomada* muda completamente o nível de profundidade da resposta.
- **Restrição também é instrução.** Explicitar o que a IA não deve fazer evita alucinação e é tão importante quanto descrever a tarefa.
- **Formato fechado gera resposta comparável.** Nomear as colunas da tabela permite rodar o mesmo prompt em períodos diferentes e comparar resultados.
- **Em contexto bancário, privacidade não é opcional.** A anonimização precisa estar no prompt, não como boa vontade do modelo.

---

*Desafio Criativo — Trilha de Prompt Engineering / DIO*
