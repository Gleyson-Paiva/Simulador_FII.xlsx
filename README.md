# Simulador de Investimentos em Fundos Imobiliários - Excel

Projeto desenvolvido para o Desafio de Projeto da DIO. O objetivo foi criar do zero uma ferramenta no Excel que simula o crescimento de patrimônio e dividendos em FIIs.

### 🚀 Funcionalidades implementadas

**1. Parâmetros com Intervalos Nomeados**
Criei os nomes `aporte_mensal`, `taxa_anual`, `taxa_mensal`, `dy_mensal`, `prazo_meses` e `perfil_atual` em Fórmulas > Definir Nome para deixar as fórmulas limpas e profissionais.

**2. Cálculo de Patrimônio com VF**
Taxa mensal convertida: `=(1+taxa_anual)^(1/12)-1`
Patrimônio final: `=VF(taxa_mensal; prazo_meses; -aporte_mensal; 0; 0)`
Total investido: `=aporte_mensal*prazo_meses`
Juros ganhos: `=Patrimônio - Total Investido`

**3. Dividendos**
Dividendo mensal final: `=Patrimônio*dy_mensal`
Dividendo anual: `=Dividendo_mensal*12`

**4. Divisão por Perfil com PROCV + Validação de Dados**
Criei a tabela de apoio `tbl_perfis`:
- Conservador: 30% Tijolo / 70% Papel
- Moderado: 50% / 50%
- Arrojado: 70% / 30%

Fórmulas:
- `=aporte_mensal*PROCV(perfil_atual; tbl_perfis; 2; FALSO)`
- `=aporte_mensal*PROCV(perfil_atual; tbl_perfis; 3; FALSO)`
Validação de dados com lista suspensa aplicada na célula do perfil.

**5. Cenários de 2 a 30 anos**
Aba com projeção para 2, 5, 10, 15, 20, 25 e 30 anos usando a mesma função VF, mostrando o poder dos juros compostos. Gráfico de linha para visualização.

### 📁 Arquivos do Repositório
- Simulador_FII_Projeto.xlsx
- /prints

### 🛠️ Tecnologias
Excel, Funções VF, PROCV, Validação de Dados, Intervalos Nomeados, Tabelas Dinâmicas
