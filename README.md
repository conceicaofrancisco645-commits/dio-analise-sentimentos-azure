# 🧠 Análise de Sentimentos com Azure AI Language

Projeto prático do bootcamp da **DIO** sobre o **Azure AI Language Studio**: análise de sentimento e extração de informações de frases.

Para aproximar o lab do meu dia a dia, escrevi frases do contexto de **logística e cadeia de suprimentos**: comentários de clientes, de fornecedores e de equipes de almoxarifado. Assim dá para avaliar se a IA serve para triar feedbacks operacionais.

---

## 🎯 Objetivo

- Criar um recurso **Azure AI Language** no portal do Azure
- Usar o **Language Studio** para analisar sentimentos e opiniões em frases
- Extrair **frases-chave** e **entidades nomeadas** dos mesmos textos
- Registrar o processo, os resultados e o que aprendi

---

## 🛠️ Tecnologias

| Ferramenta | Uso |
|---|---|
| Microsoft Azure | Criação do grupo de recursos e do serviço de linguagem |
| Azure AI Language (Language Studio) | Análise de sentimento, mineração de opinião, frases-chave, NER |
| GitHub | Documentação e portfólio |

---

## 🚀 Passo a passo

### 1. Criação do recurso no Azure
No portal do Azure, cria-se um **Resource Group** e um recurso **Language Service** no plano gratuito (F0).


### 2. Acesso ao Language Studio
No [Language Studio](https://language.cognitive.azure.com/), entra-se com a mesma conta e vincula-se o recurso criado.


### 3. Análise de sentimentos e mineração de opinião
Em **Classify text → Analyze sentiment and mine opinions**, entram as frases do arquivo [`inputs/sentencas.txt`](inputs/sentencas.txt), com idioma **Português** e *opinion mining* ativado.


### 4. Extração de frases-chave
Em **Extract information → Extract key phrases**, os mesmos textos mostram quais termos a IA considera centrais.


### 5. Reconhecimento de entidades (NER)
Em **Extract information → Find named entities**, a IA identifica locais, organizações, datas e quantidades.


---

## 📊 Resultados

> Sentimento esperado para cada frase. A coluna de confiança será preenchida com os valores retornados pelo Language Studio.

| # | Frase (resumo) | Sentimento esperado | Confiança |
|---|---|---|---|
| 1 | Entrega chegou antes do prazo e bem embalada | Positivo | a preencher |
| 2 | Pedido atrasou 10 dias e ninguém avisou | Negativo | a preencher |
| 3 | Material recebido conforme a nota fiscal | Neutro | a preencher |
| 4 | Fornecedor rápido, mas peças vieram com avaria | Misto | a preencher |
| 5 | Equipe do almoxarifado muito atenciosa | Positivo | a preencher |

---

## 💡 Insights

- **Frases mistas são o ponto forte do opinion mining.** Numa frase como "rápido, mas com avaria", a nota geral vem *mista*. A mineração de opinião separa o alvo **fornecedor/rapidez** (positivo) do alvo **peças/avaria** (negativo). Uma classificação simples perderia isso.
- **Frases factuais ficam neutras.** "Material recebido conforme a nota fiscal" não carrega emoção, e a IA não força positivo nem negativo. Isso é bom para não gerar falso alarme.
- **O contexto do domínio importa.** Termos técnicos (NF, NCR, kit, avaria) nem sempre são entendidos como um especialista entenderia. Para uso real, o caminho seria um modelo personalizado (*Custom Text Classification*).
- **Frases-chave viram indicadores.** Os termos extraídos ("atraso", "avaria", "prazo") podem alimentar um dashboard de causas de reclamação.

---

## 🔭 Possibilidades de aplicação

- **Triagem automática de feedbacks** de clientes e fornecedores: negativos vão direto para uma fila prioritária
- **Monitoramento de fornecedores**: nota de sentimento por fornecedor ao longo do tempo
- **Integração com Power BI**: sentimentos e frases-chave em um painel de qualidade do atendimento
- **Automação com Make / Power Automate**: e-mail ou formulário → Azure AI Language → planilha ou alerta no Teams
- **Pesquisas internas**: medir o clima das equipes a partir de respostas abertas

---

## 📚 O que aprendi

- Provisionar serviços cognitivos no Azure e entender o plano gratuito
- A diferença entre **sentimento do documento**, **sentimento da frase** e **opinião por alvo**
- Que a nota de confiança deve guiar decisões: resultados com confiança baixa merecem revisão humana
- Que soluções de IA prontas resolvem bem o geral, mas domínios específicos pedem personalização

---

## 📁 Estrutura do repositório

```
├── README.md
└── inputs/
    └── sentencas.txt     # frases usadas na análise
```

---

## 👤 Autor

**Francisco Conceição da Silva Santos**
Analista de Controle de Materiais em transição para Dados & BI | Power BI • Excel • Automação

[GitHub](https://github.com/conceicaofrancisco645-commits)
