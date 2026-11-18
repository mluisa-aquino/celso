# Economia e Finanças (SPOECFI) – Exercícios de Excel

Nove exercícios que acompanham a matéria, das decisões com recursos escassos até VPL/TIR/Payback, e um exercício final que junta tudo. Cada um traz os dados, o que fazer, e o **gabarito com as fórmulas e os valores esperados** (confira sua planilha com eles).

## Antes de começar

- As fórmulas estão em **Excel em português** (separador `;` e vírgula decimal). Se o seu Excel estiver em inglês, use `,` como separador e os nomes em inglês (tabela abaixo).
- Crie **um arquivo** `Economia_Financas.xlsx` com **uma aba por exercício** (nomes sugeridos em cada exercício).
- Boas práticas cobradas na disciplina: coloque os **dados de entrada em células separadas** (taxa, capital, prazo) e referencie com `$` (ex.: `$B$2`); **não digite números dentro das fórmulas**; arredonde apenas na apresentação (formato de célula), nunca dentro do cálculo.

| Português | Inglês | Uso |
|---|---|---|
| `SOMA`, `SOMARPRODUTO` | `SUM`, `SUMPRODUCT` | totais |
| `SE`, `E`, `OU` | `IF`, `AND`, `OR` | decisões |
| `MÍNIMO`, `MÁXIMO` | `MIN`, `MAX` | menor/maior valor |
| `CONT.SE`, `CORRESP`, `ÍNDICE` | `COUNTIF`, `MATCH`, `INDEX` | contar e localizar |
| `VF`, `VP`, `NPER`, `TAXA` | `FV`, `PV`, `NPER`, `RATE` | juros compostos |
| `PGTO`, `IPGTO`, `PPGTO` | `PMT`, `IPMT`, `PPMT` | PRICE |
| `VPL`, `TIR` | `NPV`, `IRR` | projetos |

**Atenção ao `VPL` do Excel**: a função desconta o **primeiro valor um período**. Por isso, o fluxo do ano 0 fica **fora** da função: `=VPL(TMA; fluxos do ano 1 em diante) + fluxo do ano 0`.

---

## Exercício 1 – Decisão com recursos limitados (Aula 1)
**Aba:** `Orcamento`. **Conceitos:** escassez, custo de oportunidade, relação custo-benefício.

**Dados** (colunas A a D, linhas 2 a 7):

| A: Alternativa | B: Custo (R$) | C: Benefício | D: Prioridade |
|---|---|---|---|
| Atualização dos computadores | 18000 | 90 | 5 |
| Treinamento dos funcionários | 12000 | 80 | 4 |
| Novo sistema ERP | 25000 | 120 | 5 |
| Marketing digital | 10000 | 55 | 3 |
| Segurança da informação | 15000 | 100 | 5 |
| Backup em nuvem | 8000 | 60 | 4 |

**Monte:**
1. Coluna **E** "Escolha" (1 = selecionar, 0 = não) e coluna **F** "Razão benefício/custo por R$ 1.000" `=C2/(B2/1000)`.
2. Em `B9` o orçamento (50000). Em `B10` o custo escolhido, em `B11` o benefício escolhido, em `B12` o saldo, em `B13` a situação.
3. Preencha a coluna E à mão para maximizar o benefício sem estourar o orçamento. Depois confirme com o **Solver** (Dados > Solver).
4. Reduza o orçamento em 20% (`=B9*0,8`) e refaça a escolha.
5. Escreva em uma célula de texto o **custo de oportunidade** da sua escolha.

**Gabarito (fórmulas):**
- `B10`: `=SOMARPRODUTO(B2:B7;E2:E7)`
- `B11`: `=SOMARPRODUTO(C2:C7;E2:E7)`
- `B12`: `=B9-B10`
- `B13`: `=SE(B10<=B9;"Dentro do orçamento";"Estourou o orçamento")`
- Solver: objetivo `B11` = máximo; variáveis `E2:E7`; restrições `B10 <= B9` e `E2:E7 = bin`.

**Valores esperados:**
- Orçamento de 50.000: escolher **Treinamento, Marketing, Segurança e Backup** → custo **45.000**, benefício **295**, saldo 5.000. (Alternativa com ERP + Segurança + Backup dá só 280.)
- Orçamento de 40.000: **Treinamento, Segurança e Backup** → custo **35.000**, benefício **240**.
- Maior razão: Backup (7,50). Razões: Atualização 5,00; Treinamento 6,67; ERP 4,80; Marketing 5,50; Segurança 6,67.

---

## Exercício 2 – Oferta, demanda e equilíbrio (Aula 2)
**Aba:** `Mercado`. **Conceitos:** lei da demanda e da oferta, equilíbrio, excedente, escassez, deslocamento.

**Parâmetros** (células): `I2` = 100 (a), `I3` = 2 (b), `I4` = 10 (c), `I5` = 1 (d). Modelo: Qd = a − b·P e Qo = c + d·P.
**Preços** em `A2:A7`: 10, 20, 30, 40, 50, 60.

**Monte:**
1. `B`: quantidade demandada. `C`: quantidade ofertada. `D`: situação (Escassez, Excedente ou Equilíbrio). `E`: tamanho do desequilíbrio.
2. `I8`: preço de equilíbrio e `I9`: quantidade de equilíbrio (por fórmula, não digitada).
3. Gráfico de **dispersão com linhas** (quantidade no eixo X, preço no eixo Y) com as duas curvas.
4. **Cenário:** a renda sobe e a demanda passa a ser Qd = 130 − 2P (mude `I2` para 130). Registre o novo equilíbrio e explique se foi movimento ou deslocamento.

**Gabarito (fórmulas):**
- `B2`: `=MÁXIMO(0;$I$2-$I$3*A2)`
- `C2`: `=$I$4+$I$5*A2`
- `D2`: `=SE(B2>C2;"Escassez";SE(B2<C2;"Excedente";"Equilíbrio"))`
- `E2`: `=ABS(B2-C2)`
- `I8`: `=(I2-I4)/(I3+I5)`; `I9`: `=I4+I5*I8`

**Valores esperados:**

| Preço | Qd | Qo | Situação | Diferença |
|---|---|---|---|---|
| 10 | 80 | 20 | Escassez | 60 |
| 20 | 60 | 30 | Escassez | 30 |
| 30 | 40 | 40 | **Equilíbrio** | 0 |
| 40 | 20 | 50 | Excedente | 30 |
| 50 | 0 | 60 | Excedente | 60 |
| 60 | 0 | 70 | Excedente | 70 |

Equilíbrio: **P = 30, Q = 40**. Com a = 130: **P = 40, Q = 50**. É um **deslocamento** da curva de demanda para a direita (mudou a renda, não o preço do bem), e o equilíbrio sobe em preço e quantidade.

---

## Exercício 3 – Painel macroeconômico (Aula 3)
**Aba:** `Macro`. **Conceitos:** PIB pela ótica da despesa, PIB nominal x real, inflação, desemprego, leitura de cenário.

**Dados** (linhas 2 a 6, valores de PIB em R$ bilhões, cesta em R$):

| A: Ano | B: C | C: I | D: G | E: X | F: M | I: Cesta de preços | N: Desempregados | O: Força de trabalho |
|---|---|---|---|---|---|---|---|---|
| 1 | 700 | 200 | 250 | 150 | 100 | 2000 | 80000 | 1000000 |
| 2 | 730 | 210 | 255 | 160 | 110 | 2140 | 75000 | 1000000 |
| 3 | 760 | 190 | 260 | 170 | 120 | 2290 | 78000 | 1000000 |
| 4 | 740 | 170 | 265 | 175 | 125 | 2450 | 95000 | 1000000 |
| 5 | 770 | 200 | 270 | 180 | 130 | 2550 | 85000 | 1000000 |

**Monte** (colunas G a Q): PIB (G), crescimento nominal (H), inflação pela cesta (J), índice de preços com base no ano 1 (K), PIB real (L), crescimento real (M), taxa de desemprego (P), diagnóstico (Q). Simplificação didática: a cesta serve de deflator.

**Gabarito (fórmulas, linha 3 como exemplo):**
- `G2`: `=B2+C2+D2+E2-F2`
- `H3`: `=(G3-G2)/G2`
- `J3`: `=(I3-I2)/I2`
- `K2`: `=I2/$I$2`
- `L2`: `=G2/K2`
- `M3`: `=(L3-L2)/L2`
- `P2`: `=N2/O2`
- `Q3`: `=SE(M3<0;"Retração real";"Expansão real")`
- Formate H, J, M e P como porcentagem; aplique formatação condicional em Q.

**Valores esperados:**

| Ano | PIB | Cresc. nominal | Inflação | PIB real | Cresc. real | Desemprego | Diagnóstico |
|---|---|---|---|---|---|---|---|
| 1 | 1.200 | – | – | 1.200,00 | – | 8,0% | – |
| 2 | 1.245 | 3,75% | 7,00% | 1.163,55 | −3,04% | 7,5% | Retração real |
| 3 | 1.260 | 1,20% | 7,01% | 1.100,44 | −5,42% | 7,8% | Retração real |
| 4 | 1.225 | −2,78% | 6,99% | 1.000,00 | −9,13% | 9,5% | Retração real |
| 5 | 1.290 | 5,31% | 4,08% | 1.011,76 | +1,18% | 8,5% | Expansão real |

**Leitura:** nos anos 2 e 3 o PIB nominal sobe, mas a produção real cai porque a inflação foi maior que o crescimento nominal (a lição do PIB nominal x real).

**Parte extra – o gestor decide:** em `S1:S4` digite PIB = 0,5%, inflação = 8%, desemprego = 10% e juros = 14%. Em `S6` escreva `=SE(E(S1<1%;S4>=12%);"Postura conservadora";"Avaliar expansão")`. Esperado: **Postura conservadora**. Mude o juro para 8% e observe a mudança.

---

## Exercício 4 – Juros simples x compostos (Aulas 5 e 6)
**Aba:** `Juros`. **Conceitos:** capitalização simples e composta, valor presente, taxa equivalente, prazo.

**Entradas:** `B1` capital = 10000; `B2` taxa = 2% (a.m.); `B3` prazo máximo = 24.

**Monte:**
1. Tabela a partir da linha 5: `A` n (0 a 24), `B` montante simples, `C` montante composto, `D` diferença, `E` juros compostos acumulados.
2. Gráfico de linhas comparando `B` e `C`.
3. Células de resumo (veja abaixo): taxa anual equivalente, VF e VP com funções financeiras, prazo para dobrar o capital e taxa implícita de uma operação.
4. **Comparação de alternativas (data focal):** A = receber 5.000 hoje; B = receber 6.000 em 6 meses, taxa 2% a.m. Calcule VP e VF das duas e decida.
5. **Efeito do prazo:** R$ 3.500 a 2,5% a.m. Calcule os juros em 8 e 16 meses e compare com o dobro dos juros de 8 meses.

**Gabarito (fórmulas):**
- `B5`: `=$B$1*(1+$B$2*A5)`; `C5`: `=$B$1*(1+$B$2)^A5`; `D5`: `=C5-B5`; `E5`: `=C5-$B$1`
- Conferência com função: `=VF($B$2;A5;;-$B$1)` deve igualar `C5`.
- Taxa anual equivalente: `=(1+B2)^12-1`
- VP: `=-VP(B2;6;;6000)` (VP de 6.000 em 6 meses)
- Prazo para dobrar: `=NPER(B2;;-B1;2*B1)`
- Taxa implícita (4.000 viram 4.600 em 5 meses, composto): `=TAXA(5;;-4000;4600)`
- Alternativa B, VP: `=6000/(1+B2)^6`; VF de A: `=5000*(1+B2)^6`
- Juros em 8 meses: `=3500*((1+2,5%)^8-1)`

**Valores esperados:**

| n | Simples | Composto | Diferença |
|---|---|---|---|
| 6 | 11.200,00 | 11.261,62 | 61,62 |
| 12 | 12.400,00 | 12.682,42 | 282,42 |
| 24 | 14.800,00 | 16.084,37 | 1.284,37 |

- Taxa anual equivalente a 2% a.m.: **26,82%** (e não 24%).
- VP de 6.000 em 6 meses: **5.327,83**. Prazo para dobrar o capital: **35,00 meses** (≈ 35,003).
- Taxa implícita (4.000 → 4.600 em 5 meses): **2,83% a.m.** (≈ 2,8347%).
- Data focal: VP(A) = 5.000,00 e VP(B) = **5.327,83**; VF(A) = **5.630,81** e VF(B) = 6.000,00. **B vence nas duas datas.**
- Prazo: J(8 meses) = **764,41**; J(16 meses) = **1.695,77**; o dobro de J(8) seria 1.528,82. Dobrar o prazo faz os juros compostos crescerem mais que o dobro.
- Pergunta: por que no primeiro período o simples e o composto coincidem? (Em n = 1 só existe a base inicial para render juros.)

---

## Exercício 5 – Fluxo de caixa projetado (Aula 7)
**Aba:** `Caixa`. **Conceitos:** entradas, saídas, fluxo líquido, saldo, insuficiência de caixa dentro do período.

**Entradas:** `B1` saldo inicial = 15000; `B2` inadimplência (percentual das entradas não recebidas) = 0%.

| A: Mês | B: Entradas | C: Saídas |
|---|---|---|
| 1 | 50000 | 48000 |
| 2 | 46000 | 52000 |
| 3 | 44000 | 60000 |
| 4 | 58000 | 50000 |
| 5 | 62000 | 55000 |
| 6 | 40000 | 58000 |

Coloque a tabela nas linhas 4 a 9 e preencha `D` (fluxo líquido), `E` (saldo final) e `F` (alerta).

**Monte:**
1. Fluxo líquido e saldo acumulado mês a mês, com **formatação condicional** vermelha para saldo negativo.
2. Resumo: menor saldo, mês do menor saldo, quantidade de meses negativos e **necessidade de capital de giro** (quanto faltaria).
3. **Cenário:** altere `B2` para 10% e refaça a leitura (as entradas passam a valer `B*(1-$B$2)`).
4. Responda: fluxo líquido negativo significa saldo final negativo? Compare mês 2 e mês 3.

**Gabarito (fórmulas):**
- `D4`: `=B4*(1-$B$2)-C4`
- `E4`: `=$B$1+D4`; `E5`: `=E4+D5` (arraste)
- `F4`: `=SE(E4<0;"CAIXA NEGATIVO";"OK")`
- Menor saldo: `=MÍNIMO(E4:E9)`
- Mês do menor saldo: `=ÍNDICE(A4:A9;CORRESP(MÍNIMO(E4:E9);E4:E9;0))`
- Meses negativos: `=CONT.SE(E4:E9;"<0")`
- Necessidade de capital de giro: `=MÁXIMO(0;-MÍNIMO(E4:E9))`

**Valores esperados (inadimplência 0%):**

| Mês | Fluxo líquido | Saldo |
|---|---|---|
| 1 | 2.000 | 17.000 |
| 2 | −6.000 | 11.000 |
| 3 | −16.000 | **−5.000** |
| 4 | 8.000 | 3.000 |
| 5 | 7.000 | 10.000 |
| 6 | −18.000 | **−8.000** |

Menor saldo = **−8.000 (mês 6)**; meses negativos = **2** (3 e 6); necessidade de capital de giro = **8.000**.
No mês 2 o fluxo é negativo (−6.000) e o saldo ainda é positivo (11.000), porque havia saldo anterior.

**Com 10% de inadimplência:** saldos de **12.000; 1.400; −19.000; −16.800; −16.000; −38.000**. Meses negativos = **4**, menor saldo = **−38.000 (mês 6)**. Uma perda de 10% nas entradas multiplica a necessidade de caixa.

---

## Exercício 6 – Tabela PRICE (Aula 8)
**Aba:** `PRICE`. **Conceitos:** prestação constante, juros sobre o saldo, amortização crescente, saldo devedor.

**Entradas:** `B1` capital = 45000; `B2` taxa = 1,5% a.m.; `B3` prazo = 10 meses.

**Monte:**
1. `B4`: prestação com `PGTO`.
2. Tabela (linhas 7 a 16, meses 1 a 10): `A` mês, `B` saldo inicial, `C` juros, `D` amortização, `E` saldo final, `F` prestação.
3. Totais: juros, amortização e total pago.
4. **Verificação:** compare `C` e `D` com `IPGTO` e `PPGTO`; confirme que o saldo final do último mês é zero.
5. Calcule o percentual de juros dentro da 1ª e da última prestação e o saldo devedor após a 5ª prestação.

**Gabarito (fórmulas):**
- `B4`: `=-PGTO(B2;B3;B1)`
- `B7`: `=B1`; `B8`: `=E7` (arraste)
- `C7`: `=B7*$B$2`
- `D7`: `=$B$4-C7`
- `E7`: `=B7-D7`
- `F7`: `=$B$4`
- Total de juros: `=SOMA(C7:C16)`; total pago: `=SOMA(F7:F16)`
- Verificação: `=-IPGTO($B$2;A7;$B$3;$B$1)` e `=-PPGTO($B$2;A7;$B$3;$B$1)`
- Saldo zero: `=ARRED(E16;2)`
- % de juros na 1ª prestação: `=C7/F7`

**Valores esperados:** prestação = **R$ 4.879,54**.

| Mês | Juros | Amortização | Saldo final |
|---|---|---|---|
| 1 | 675,00 | 4.204,54 | 40.795,46 |
| 2 | 611,93 | 4.267,61 | 36.527,86 |
| 3 | 547,92 | 4.331,62 | 32.196,24 |
| 4 | 482,94 | 4.396,59 | 27.799,64 |
| 5 | 416,99 | 4.462,54 | **23.337,10** |
| 6 | 350,06 | 4.529,48 | 18.807,62 |
| 7 | 282,11 | 4.597,42 | 14.210,19 |
| 8 | 213,15 | 4.666,39 | 9.543,81 |
| 9 | 143,16 | 4.736,38 | 4.807,43 |
| 10 | 72,11 | 4.807,43 | 0,00 |

Total de juros ≈ **R$ 3.795,38**; total pago ≈ **R$ 48.795,38**. Juros: **13,83%** da 1ª prestação e **1,48%** da última. A prestação é constante, os juros caem e a amortização cresce.

---

## Exercício 7 – SAC e comparação com PRICE (Aula 9)
**Aba:** `SAC`. **Conceitos:** amortização constante, prestação decrescente, comparação SAC x PRICE, limite de pagamento.

**Entradas:** use os mesmos dados do Exercício 6 (capital 45.000; 1,5% a.m.; 10 meses) e a prestação PRICE da aba `PRICE` (`=PRICE!B4`). `B5` = limite mensal de pagamento da empresa = 5000.

**Monte:**
1. Tabela SAC (linhas 8 a 17): `A` mês, `B` saldo inicial, `C` amortização, `D` juros, `E` prestação SAC, `F` saldo final, `G` prestação PRICE, `H` menor prestação, `I` SAC dentro do limite? (sim/não), `J` PRICE dentro do limite?
2. Totais de juros dos dois sistemas e a diferença.
3. Primeiro mês em que a prestação SAC fica menor que a PRICE.
4. Quantos meses o SAC passa do limite de R$ 5.000? E o PRICE?
5. Confirme com `VPL` que o valor presente dos pagamentos é 45.000 nos dois sistemas.
6. Gráfico de colunas das prestações SAC e PRICE.

**Gabarito (fórmulas):**
- `C8`: `=$B$1/$B$3` (amortização constante)
- `D8`: `=B8*$B$2`
- `E8`: `=C8+D8`
- `F8`: `=B8-C8`; `B9`: `=F8` (arraste)
- `G8`: `=PRICE!$B$4`
- `H8`: `=SE(E8<G8;"SAC";"PRICE")`
- `I8`: `=SE(E8<=$B$5;"Sim";"Não")`; `J8`: `=SE(G8<=$B$5;"Sim";"Não")`
- Total de juros SAC: `=SOMA(D8:D17)`; total PRICE: `=SOMA(PRICE!C7:C16)`
- Primeiro mês com SAC menor: `=CORRESP("SAC";H8:H17;0)`
- Meses acima do limite no SAC: `=CONT.SE(E8:E17;">"&B5)`
- VP: `=VPL($B$2;E8:E17)` e `=VPL($B$2;G8:G17)` (ambos devem dar 45.000)

**Valores esperados:** amortização = **4.500,00**.

| Mês | Prestação SAC | Prestação PRICE | Menor |
|---|---|---|---|
| 1 | 5.175,00 | 4.879,54 | PRICE |
| 2 | 5.107,50 | 4.879,54 | PRICE |
| 3 | 5.040,00 | 4.879,54 | PRICE |
| 4 | 4.972,50 | 4.879,54 | PRICE |
| 5 | 4.905,00 | 4.879,54 | PRICE |
| 6 | 4.837,50 | 4.879,54 | **SAC** |
| 7 | 4.770,00 | 4.879,54 | SAC |
| 8 | 4.702,50 | 4.879,54 | SAC |
| 9 | 4.635,00 | 4.879,54 | SAC |
| 10 | 4.567,50 | 4.879,54 | SAC |

- Juros totais: SAC = **3.712,50**; PRICE = **3.795,38**; diferença ≈ **82,88** (SAC menor).
- A prestação SAC fica menor que a PRICE a partir do **mês 6**.
- Com limite de 5.000: o SAC ultrapassa em **3 meses** (1, 2 e 3); o PRICE em **nenhum**.
- VP dos dois sistemas = **45.000** (mesma taxa; só muda a distribuição no tempo).
- Redução entre prestações SAC = 4.500 × 1,5% = **67,50**.

---

## Exercício 8 – VPL, TIR, Payback e TMA (Aulas 10 e 11)
**Aba:** `Projeto`. **Conceitos:** fluxo de caixa de projeto, TMA, VPL, TIR, Payback simples e descontado, sensibilidade.

**Entradas:** `B1` TMA = 10%; `B2` prazo máximo de Payback = 3,5 anos.

**Fluxos** (colunas A e B, linhas 5 a 10):

| A: Ano | B: Fluxo |
|---|---|
| 0 | −100000 |
| 1 | 25000 |
| 2 | 30000 |
| 3 | 35000 |
| 4 | 40000 |
| 5 | 45000 |

**Monte:**
1. `C` fluxo acumulado, `D` valor presente de cada fluxo, `E` VP acumulado.
2. VPL (de duas formas), TIR, Payback simples e Payback descontado.
3. Decisão automática com `SE`.
4. **Tabela de sensibilidade:** VPL com TMA de 5%, 8%, 10%, 12%, 15%, 20% e 25%. Em que faixa a TIR está?
5. **Estudo de caso** (arquivo `TIR_Payback.pdf`): em outra área da aba, calcule soma das entradas, VPL, TIR e Payback dos projetos A e B (investimento 60.000; A: 20.000/25.000/30.000; B: 35.000/20.000/10.000; TMA 10%; limite de Payback 2,7 anos) e escolha um.

**Gabarito (fórmulas):**
- `C5`: `=SOMA($B$5:B5)`
- `D5`: `=B5/(1+$B$1)^A5`
- `E5`: `=SOMA($D$5:D5)`
- VPL (função): `=VPL(B1;B6:B10)+B5`; VPL (soma dos VPs): `=SOMA(D5:D10)` (devem coincidir)
- TIR: `=TIR(B5:B10)`
- Prova da TIR: `=VPL(TIR(B5:B10);B6:B10)+B5` deve dar 0 (ou valor muito próximo)
- Payback parcial, na coluna `F` (linhas 5 a 9): `=SE(E(C5<0;C6>=0);A5+(-C5)/B6;"")`; Payback simples = `=SOMA(F5:F9)`
- Payback descontado, na coluna `G`: `=SE(E(E5<0;E6>=0);A5+(-E5)/D6;"")`; total `=SOMA(G5:G9)`
- Decisão: `=SE(E(VPL>0;TIR>B1;Payback<=B2);"Aprovar";"Revisar")` (substitua pelos endereços das células)
- Sensibilidade: `=VPL(taxa;$B$6:$B$10)+$B$5`, com a taxa na coluna ao lado

**Valores esperados (projeto principal):**

| Ano | Fluxo | Acumulado | VP | VP acumulado |
|---|---|---|---|---|
| 0 | −100.000 | −100.000 | −100.000,00 | −100.000,00 |
| 1 | 25.000 | −75.000 | 22.727,27 | −77.272,73 |
| 2 | 30.000 | −45.000 | 24.793,39 | −52.479,34 |
| 3 | 35.000 | −10.000 | 26.296,02 | −26.183,32 |
| 4 | 40.000 | 30.000 | 27.320,54 | 1.137,22 |
| 5 | 45.000 | 75.000 | 27.941,46 | 29.078,68 |

- **VPL (10%) = R$ 29.078,68**; **TIR ≈ 19,71%**; **Payback simples = 3,25 anos** (3 anos e 3 meses); **Payback descontado ≈ 3,96 anos**.
- Decisão: VPL > 0, TIR > TMA e Payback (3,25) ≤ 3,5 → **Aprovar**.
- Sensibilidade do VPL:

| TMA | VPL |
|---|---|
| 5% | 49.421,50 |
| 8% | 36.679,88 |
| 10% | 29.078,68 |
| 12% | 22.104,49 |
| 15% | 12.679,59 |
| 20% | **−704,09** |
| 25% | −11.750,40 |

O VPL muda de sinal entre 15% e 20%, o que confirma a TIR de ≈ 19,71%. Conclusão: quanto maior a TMA, menor o VPL.

**Estudo de caso (valores esperados):**

| | Projeto A | Projeto B |
|---|---|---|
| Soma das entradas | 75.000 | 65.000 |
| VPL (10%) | **+1.382,42** | **−4.139,74** |
| TIR | 11,22% (> 10%) | 5,12% (< 10%) |
| Payback simples | 2,5 anos | 2,5 anos |
| Atende 2,7 anos? | Sim | Sim |

**Escolha: A.** Os dois empatam no Payback e passam no limite, mas só A tem VPL positivo e TIR acima da TMA. Escolher só pelo Payback não distinguiria os projetos e ignoraria o valor do dinheiro no tempo.

---

## Exercício 9 – Integrador: financiar e avaliar um projeto (Aulas 5 a 11)
**Aba:** `Integrador`. **Conceitos:** PRICE x SAC, fluxo de caixa, limite de pagamento, VPL, TIR mensal e anual, Payback, decisão.

**Situação:** uma empresa compra equipamentos de **R$ 60.000** financiados em **12 meses a 1,8% a.m.**. O projeto gera **R$ 6.000 por mês** durante 12 meses. A **TMA é 1,5% a.m.** e a empresa só consegue destinar **R$ 5.800 por mês** ao financiamento.

**Entradas:** `B1` = 60000; `B2` = 1,8%; `B3` = 12; `B4` (fluxo mensal do projeto) = 6000; `B5` (TMA) = 1,5%; `B6` (limite) = 5800.

**Monte e responda:**
1. Tabela de 12 meses com a prestação **PRICE** e a prestação **SAC** (e seus juros e saldos).
2. Total de juros de cada sistema e a diferença.
3. Em quantos meses cada sistema passa do limite de R$ 5.800? Em que mês o SAC fica menor que a PRICE?
4. Fluxo líquido mensal depois do financiamento (`B4 − prestação`) nos dois sistemas. Algum mês fica negativo?
5. Fluxo do projeto (−60.000 e 12 vezes 6.000): VPL à TMA, TIR mensal, TIR anual equivalente e Payback.
6. VPL do projeto usando a taxa do financiamento (1,8%) no lugar da TMA. O que isso mostra?
7. Escreva a **recomendação final** (qual sistema e se o projeto deve ser feito), citando VPL, TIR, Payback e a restrição de caixa.

**Gabarito (fórmulas principais):**
- PRICE: `=-PGTO($B$2;$B$3;$B$1)`; SAC: amortização `=$B$1/$B$3`, juros `=saldo*$B$2`, prestação `=amortização+juros`
- Meses acima do limite: `=CONT.SE(intervalo;">"&$B$6)`
- Primeiro mês com SAC menor: use uma coluna `=SE(SAC<PRICE;"SAC";"PRICE")` e `=CORRESP("SAC";coluna;0)`
- Fluxo líquido: `=$B$4-prestação`
- VPL: `=VPL($B$5;fluxos de 1 a 12)+fluxo0`; TIR: `=TIR(fluxos)`; TIR anual: `=(1+TIR)^12-1`
- Payback: `=B1/B4` (fluxos constantes)

**Valores esperados:**
- **PRICE:** prestação **R$ 5.604,12**; total de juros **R$ 7.249,42**.
- **SAC:** amortização 5.000,00; prestações de **6.080,00** (mês 1) até **5.090,00** (mês 12); total de juros **R$ 7.020,00**. O SAC é R$ 229,42 mais barato em juros nominais.
- **Limite de 5.800:** o SAC passa em **4 meses** (6.080; 5.990; 5.900; 5.810). O PRICE em **nenhum**.
- O SAC fica menor que a PRICE a partir do **mês 7** (5.540 contra 5.604,12).
- **Fluxo líquido mensal:** PRICE = **+395,88** todos os meses. SAC = **−80,00** no mês 1, +10,00 no mês 2, +100,00 no mês 3, e assim por diante, até **+910,00** no mês 12.
- **Projeto:** VPL a 1,5% a.m. = **R$ 5.445,03**; TIR ≈ **2,92% a.m.** (≈ **41,30% a.a.**); Payback = **10 meses** (60.000 / 6.000).
- VPL a 1,8% a.m. = **R$ 4.238,47** (continua positivo: o projeto rende mais que o custo do financiamento).
- **Recomendação esperada:** fazer o projeto, pois VPL > 0, TIR > TMA e Payback de 10 meses dentro do horizonte de 12. Financiar pelo **PRICE**: atende ao limite de R$ 5.800 em todos os meses e mantém o fluxo líquido positivo. O SAC custa menos juros, mas estoura o limite e deixa o caixa negativo no mês 1.

---

## Roteiro de estudo sugerido
1. Faça os exercícios na ordem. Cada um usa conceitos do anterior (do 6 ao 9 em especial).
2. Antes de abrir o gabarito, confira os **testes de consistência**: saldo final da PRICE e do SAC igual a zero; VP dos pagamentos igual ao capital financiado; VPL na TIR igual a zero; composto ≥ simples para n > 1.
3. Sempre que mudar um dado de entrada (taxa, prazo, TMA), veja o que muda no resultado. É assim que você aprende o efeito de cada variável, como pedem as atividades práticas da disciplina.
