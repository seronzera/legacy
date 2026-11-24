<p align="center"><img src="img/banner.jpg" alt="Legacy" width="100%"></p>

# Quanto vale o Legacy?

<table>
<tr>
<td align="center" width="33%"><h1>US$ 5,45 mi</h1>para reconstruir o Legacy do zero nos EUA</td>
<td align="center" width="33%"><h1>286</h1>meses de trabalho de engenharia</td>
<td align="center" width="33%"><h1>13</h1>engenheiros por quase 2 anos</td>
</tr>
</table>

Se uma empresa nos Estados Unidos quisesse construir hoje tudo o que existe no Legacy, com a mesma quantidade de
código, ela gastaria cerca de **US$ 5,45 milhões** (US$ 5.450.586). Esse é o valor que ela pagaria em salários e
encargos para uma equipe de 13 engenheiros trabalhar por 22 meses.

Esse número é o **custo de reposição**: quanto custa refazer o projeto. Não é um preço de venda. O preço de venda
depende de quem compra, de quantas pessoas usam e de quanto o projeto fatura, e pode ficar abaixo ou acima desse
valor.

## O que entra na conta

O Legacy tem **47.057 linhas de código**, sem contar comentários e linhas em branco.

| Parte | O que é | Linhas | Quanto custa refazer |
| --- | --- | ---: | ---: |
| **Legacy Engine e Times Square** | O motor com ray tracing, os shaders e o jogo | 32.559 | US$ 4.340.980 |
| **Ferramentas de conteúdo** | Os programas que geram a cidade, os prédios, as pessoas e os carros | 11.562 | US$ 895.752 |
| **Plataforma** | O Legacy Launcher, o servidor de contas e o site | 2.936 | US$ 213.854 |
| **Total** | | **47.057** | **US$ 5.450.586** |

O motor é a parte mais cara: renderização em tempo real com ray tracing é um dos tipos de software mais difíceis de
fazer, e os engenheiros que fazem esse trabalho ganham mais que a média.

## O que não entra na conta

- A marca, o domínio e a empresa
- Os servidores no ar, os downloads e os jogadores
- As bibliotecas de terceiros que o motor usa

## Como o valor foi calculado

O cálculo segue o **COCOMO II**, um modelo público e muito usado para estimar quanto custa desenvolver um software a
partir do tamanho do código. Os salários são dados oficiais do governo dos EUA.

<details><summary><b>Ver a conta completa</b></summary>

<br>

**1. Esforço.** O COCOMO II calcula o esforço como 2,94 × (milhares de linhas)^E. O expoente E vem de cinco fatores
de escala do projeto, que somam 18,10: E = 0,91 + 0,01 × 18,10 = 1,091.

| Fator | Nível | Valor | Motivo |
| --- | --- | --- | --- |
| PREC (precedentes) | Baixo | 4,96 | Motor próprio com ray tracing, sem base anterior |
| FLEX (flexibilidade) | Alto | 2,03 | Requisitos definidos pela própria equipe |
| RESL (arquitetura e riscos) | Nominal | 4,24 | Valor padrão |
| TEAM (coesão da equipe) | Alto | 2,19 | Equipe pequena e única |
| PMAT (maturidade do processo) | Nominal | 4,68 | Valor padrão |

2,94 × 47,057^1,091 = 196,4 meses, divididos entre as partes pelo tamanho de cada uma.

**2. Dificuldade de cada parte.** O modelo multiplica o esforço de cada parte pela sua complexidade.

| Parte | Multiplicadores | Produto | Meses |
| --- | --- | ---: | ---: |
| Motor e jogo | Complexidade muito alta 1,34 × tempo real 1,11 × reutilizável 1,07 | 1,592 | 135,9 → 216,4 |
| Ferramentas de conteúdo | Complexidade alta 1,17 (geometria procedural) | 1,170 | 48,3 → 56,5 |
| Plataforma | Confiabilidade alta 1,10 (contas e segurança) | 1,100 | 12,3 → 13,5 |
| **Total** | | | **286,3** |

**3. Prazo e equipe.** Prazo = 3,67 × 286,3^0,3162 = 22,0 meses; equipe = 286,3 ÷ 22,0 = 13,0 pessoas em média.

**4. Custo.** Salário anual nos EUA ÷ 12 × 1,4. O fator 1,4 cobre os encargos do empregador: em março de 2025, os
benefícios eram 29,7% do custo total de um funcionário (salário ÷ 0,703 = salário × 1,42).

| Parte | Salário anual | Custo por mês | Meses | Custo |
| --- | ---: | ---: | ---: | ---: |
| Motor e jogo | US$ 171.980 (percentil 75) | US$ 20.064 | 216,4 | US$ 4.340.980 |
| Ferramentas de conteúdo | US$ 135.980 (mediana) | US$ 15.864 | 56,5 | US$ 895.752 |
| Plataforma | US$ 135.980 (mediana) | US$ 15.864 | 13,5 | US$ 213.854 |
| **Total** | | | **286,3** | **US$ 5.450.586** |

Só em salários, sem os encargos, o valor seria US$ 3.893.276.

</details>

## Fontes

- [Overview of COCOMO II, Universidade do Texas em Arlington](https://ranger.uta.edu/~khalili/Overview%20of%20COCOMO.htm): fórmulas, constantes e tabelas do modelo
- [Bureau of Labor Statistics: mediana de desenvolvedores de software nos EUA](https://api.bls.gov/publicAPI/v1/timeseries/data/OEUN000000000000015125213): US$ 135.980 por ano
- [Bureau of Labor Statistics: percentil 75 de desenvolvedores de software nos EUA](https://api.bls.gov/publicAPI/v1/timeseries/data/OEUN000000000000015125214): US$ 171.980 por ano
- [Bureau of Labor Statistics: custo do empregador, março de 2025](https://www.bls.gov/opub/ted/2025/compensation-costs-for-private-industry-averaged-45-38-per-hour-worked-in-march-2025.htm): salários 70,3% e benefícios 29,7%
- Contagem de linhas: código-fonte do Legacy em 24/11/2026 (cloc, sem comentários e linhas em branco)

<p align="center"><sub>Avaliação de novembro de 2026 · <a href="README.md">Voltar para o Legacy</a></sub></p>
