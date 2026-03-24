# PriceIQ — Analisador de Elasticidade de Preços

## Por qual motivo resolvi criar essa aplicação web?

Eu sempre recebia propostas de promoção da equipe comercial — desconto de 15% aqui, leve 3 pague 2 ali — e precisava decidir na hora da reunião se aprovava ou não. Minha única base era intuição e histórico na cabeça. Não tinha como saber se aquele desconto ia gerar volume suficiente para compensar, nem se uma mecânica de bundle fazia mais sentido do que um desconto direto para o meu perfil de clientes.

O processo era lento, subjetivo e arriscado. Às vezes eu aprovava promoções que poderiam onerar margem sem ganhar volume. Às vezes eu recusava ações que teriam funcionado.

---

## O que essa aplicação faz?

Você importa seu histórico de sell-out em CSV — data, produto, preço praticado, quantidade vendida e se havia promoção naquela semana — e a aplicação faz três coisas:

**Calcula a elasticidade real de cada produto.** Usando regressão estatística, ela separa quanto do volume extra veio da variação de preço e quanto veio do efeito da promoção em si (exposição, comunicação, impulso de compra). São dois números distintos que antes apareciam como um só.

**Simula cenários antes de você decidir.** Você escolhe o produto, define a variação de preço e o tipo de ação, e a aplicação projeta o volume esperado e o impacto na receita. O veredicto aparece imediatamente: ação favorável, neutra ou desfavorável.

**Compara mecânicas promocionais lado a lado.** Desconto direto de 15%, leve 3 pague 2, leve 3 ganhe 20% na 3ª unidade — as três rodam ao mesmo tempo com os parâmetros do seu negócio. Um gráfico mostra exatamente a partir de qual percentual de clientes multi-unidade cada mecânica passa a compensar.

---

## Como pode adotar esse simulador para sua rotina?

Antes de aprovar qualquer promoção, abra o simulador, insira os parâmetros da proposta e obtenha o resultado em 30 segundos. A reunião comercial deixará de ser uma negociação no escuro e virará uma conversa baseada em número concreto.

Fica mais fácil também recusar ações sem parecer arbitrário — o dado está ali, visível para todo mundo na tela.

---

## Como usar

**1. Prepare seu CSV**

O arquivo precisa ter estas colunas:

| Coluna | Exemplo | O que é |
|---|---|---|
| `data` | 2024-01-15 | Data da semana de venda |
| `produto` | Suco Laranja 1L | Nome ou SKU |
| `categoria` | Bebidas | Categoria do produto |
| `preco` | 8.90 | Preço praticado naquela semana |
| `quantidade` | 320 | Unidades vendidas |
| `promocao` | Desconto 11% | Tipo de promoção (deixe em branco se não havia) |

Você pode baixar um exemplo dentro da própria aplicação, na tela inicial.

**2. Importe o arquivo**

Clique em "↑ Importar CSV" na barra lateral. A aplicação processa tudo automaticamente e já exibe os resultados.

**3. Explore as quatro telas**

- **Visão geral** — panorama do portfólio com elasticidade e receita por produto
- **Elasticidade** — curva preço × demanda, impacto das promoções e distribuição do portfólio
- **Simulador** — projete o impacto de qualquer mudança de preço ou promoção antes de decidir
- **Comparador** — coloque três mecânicas promocionais lado a lado e veja qual gera mais resultado para o seu mix de clientes

**4. Atualize quando quiser**

Exportou dados novos do seu sistema? Importe o CSV atualizado e todos os cálculos se recalculam automaticamente.

---

**IMPORTANTE**

Essa aplicação roda localmente no seu navegador, dessa forma, **nenhum dado fica salvo ao sair da página**. Com isso, seus dados de venda e estratégias comerciais não ficam desprotegidos e vulneráveis a vazamentos.


## Feito com vibecoding 🤖

Não sou desenvolvedor. Construí isso usando IA como ferramenta de desenvolvimento. Se eu consegui, você também consegue.

Todo o projeto — cálculo de elasticidade, simulador, comparador de mecânicas — foi construído em conversas com IA, explicando o problema em linguagem comercial e refinando o resultado aos poucos.

Se você tem um problema repetitivo no seu trabalho que envolve dados e decisão, provavelmente dá para construir algo parecido.
