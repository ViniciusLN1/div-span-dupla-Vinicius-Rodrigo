## Rodada 1 - Pessoa A
### LLM utilizada: GEMINI 2.5 Flash

- Prompt 1 - "Explique, em até 4 linhas, a diferença entre elementos block-level e inline-level, com 2 exemplos reais de cada e quando usar DIV e SPAN. " 
Data e hora: 19:30 | 13/10


- Resposta 1 - Elementos block-level (exs: <div>, <p>) ocupam toda a largura disponível, forçam uma nova linha antes e depois, e aceitam altura e largura. Já elementos inline-level (exs: <span>, <a>) ocupam apenas o espaço necessário ao seu conteúdo e não forçam quebras de linha. Use <div> para estruturar seções maiores (bloco) e <span> para estilizar pequenos trechos de texto dentro de um bloco (em linha).



- Prompt 2 - "Gere uma página mínima sobre “DIV x SPAN”:3 cartões organizados com DIV (block) e textos/ícones com SPAN(inline). Use HTML semântico, CSS externo e comentários no código. Sem frameworks. " 
Data e hora: 19:32 | 13/10


- Resposta 2 - Entendido. Como solicitado, vou gerar o código para uma página mínima comparando <div> e <span>, usando HTML semântico, CSS externo (simulado) e comentários, com 3 cartões.

Estrutura de Arquivos

Para seguir a regra do CSS externo, você precisará de dois arquivos:

    index.html (o conteúdo da página)

    estilos.css (a estilização)



- Prompt 3 - "Ajuste o CSS para evidenciar content/padding/border/margin com cores e bordas. Explique em 3 linhas como cada camada afeta o layout. " 
Data e hora: 19:34 | 13/10


- Resposta 3 - Certamente! Vou ajustar o CSS para o modelo de caixa (Content, Padding, Border, Margin) e, em seguida, dar a explicação.

Explicação do Modelo de Caixa (3 Linhas)

    Content é a área principal (texto, imagem) e sua dimensão é alterada por width/height.

    Padding adiciona espaço interno entre o Content e a Border, influenciando o tamanho visível do bloco.

    Border é a linha que circunda o Padding/Content; Margin adiciona espaço transparente externo, separando o elemento de outros.

    

## Rodada 2 – Pessoa B (Revisor)

### LLM utilizada: ChatGPT 4 (versão gratuita)

### Revisão e alterações realizadas:

- Corrigi um erro de estrutura HTML no segundo cartão: havia um `<div>` dentro de um `<p>`, o que é inválido segundo as regras do HTML. 
- Substituí o `<div class="bloco-div">DIV</div>` por `<span class="bloco-div">DIV</span>`, mantendo o efeito visual e corrigindo a semântica.
- Testei a página no navegador e confirmei que a alteração não afeta a aparência original.
- **Sugestão para próxima rodada (Pessoa A na Rodada 2):** aplicar um estilo visual na classe `.bloco-div` no `style.css`, para deixar mais clara a diferença entre elementos block-level e inline-level. Exemplo: borda azul tracejada, fundo claro e fonte monoespaçada.

## Comparação entre LLMs (Gemini 2.5 Flash vs ChatGPT 4)

- **Prompt 1 (conceito)**: Ambas as LLMs explicaram corretamente a diferença entre elementos block-level e inline-level, com exemplos e quando usar DIV e SPAN. O ChatGPT foi um pouco mais direto e objetivo, enquanto o Gemini usou uma explicação um pouco mais detalhada. As duas respostas são claras e corretas.

- **Prompt 2 (código HTML + CSS)**: Ambas as LLMs geraram uma página funcional e clara com 3 cartões usando DIV para blocos e SPAN para ícones/textos inline. A resposta do ChatGPT é mais sucinta, com HTML semântico limpo e CSS externo simplificado, enquanto a Gemini detalhou mais comentários e estrutura.

- **Prompt 3 (CSS e explicação do box model)**: As duas LLMs explicaram corretamente o modelo de caixa e usaram cores e bordas para evidenciar content, padding, border e margin. A resposta do ChatGPT trouxe comentários mais didáticos no CSS, facilitando o entendimento.

- **Prompt 4** - "Transforme alguns <span> em blocos com display:block, aplique width:200px; height:60px; e descreva o efeito em relação ao span inline."  
Data e hora: 17:11 | 15/10/2025  
Resposta: Criei uma página com um span que, ao receber display:block e dimensões fixas, se comporta como um bloco, quebrando linha, aceitando largura e altura. Mantive comentários no código para facilitar o entendimento.  
LLM usada: ChatGPT 4

- **Prompt 5** - "Crie uma página HTML que mostre a diferença visual entre 3 DIVs empilhadas e 4 SPANs em linha. Explique o layout."
Data e hora: (17:36 | 15/10/2025)
Resposta: Criei uma página com duas colunas, uma com 3 divs empilhadas que ocupam toda largura e outra com 4 spans inline que ficam lado a lado. A página mostra claramente como divs são block e spans inline.
LLM usada: ChatGPT 4

- **Prompt 6** - "Mostre o uso do display:inline-block em spans, com largura e altura fixas. Explique o efeito visual."
Data e hora: (17:38 | 15/10/2025)
Resposta: Criei uma página demonstrando spans com display:inline-block, que ficam na mesma linha mas aceitam largura e altura. Isso diferencia inline-block do inline padrão.
LLM usada: ChatGPT 4



## Rodada 3 - Pessoa A e B (Bugs e correções)

- prompt 7 - "Analise este código (colar codigo-com-bugs.html). Liste problemas relacionados a display/width/height/margens em elementos inline, explique por que estão errados e forneça a versão corrigida."
Data e hora: (19:42 | 15/10/2025)

Resposta - Excelente pedido! O código fornecido contém vários erros de sintaxe e estrutura, mas vou focar especificamente nos problemas que afetam o comportamento de elementos inline (como <span>) no que diz respeito a display, width, height e margin, conforme solicitado.

No entanto, o erro mais crítico que impacta o layout (e, indiretamente, o uso de width/height/margin em span) é a estrutura caótica da seção principal.


Análise e Correção dos Problemas

O código apresenta o seguinte trecho problemático:
HTML

<H1>DIV (Block) vs SPAN (Inline) <div class="cartao">
    </div class="cartao"> <div class="cartao">
    </p> </div>

Este trecho mistura <h1> com <div> de forma incorreta e contém tags de fechamento inválidas.

Erros Críticos no Código Fornecido:

1. Tag <h1> não fechada e aninhamento incorreto:

HTML


<H1>DIV (Block) vs SPAN (Inline) <div class="cartao">...


O <h1> engole o primeiro <div class="cartao">. Isso é um erro grave de aninhamento.

2. Atributo na tag de fechamento:
HTML

</div class="cartao">

Isso é sintaxe inválida. Tags de fechamento não aceitam atributos.

3. Tag <span> não fechada:
HTML

A <span class="bloco-div">DIV é ideal para ... a todo o bloco.
</p> </div>

4. A tag <span> nunca é fechada, o que faz com que o elemento seja "esticado" ou tenha seu escopo de estilo vazado.


**codigo corrigido esta no arquivo correcoes.md**