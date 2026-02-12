# Web Scraping Project - Reddit API

![Python](https://img.shields.io/badge/Python-3.12+-blue.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)

Projeto de web scraping para coletar e analisar dados do Reddit usando a API PRAW (Python Reddit API Wrapper).

Esse projeto foi realizado para a realização do artigo científico "Domestic Violence-Related Head and Neck Injuries: Social Media Web-Scraping”, que foi publicado na revista Dental Traumatology.

- link: https://pubmed.ncbi.nlm.nih.gov/40799068/

## ⚠️ Aviso Legal

Este projeto foi desenvolvido apenas para fins educacionais e de pesquisa. Certifique-se de:

- Respeitar os [Termos de Serviço do Reddit](https://www.reddit.com/wiki/api)
- Não fazer requisições excessivas à API
- Respeitar a privacidade dos usuários
- Usar os dados coletados de forma ética e legal (LGPD/GDPR)

## 📝 Sobre o Projeto

Este projeto permite coletar posts de subreddits específicos do Reddit, processar os dados e exportá-los para análise. Atualmente configurado para coletar dados do subreddit "domesticviolencehelp" com filtros personalizáveis.

### Funcionalidades:

- ✅ Coleta de posts via Reddit API
- ✅ Filtragem por palavras-chave
- ✅ Processamento com Pandas
- ✅ Exportação para Excel (.xlsx)
- ✅ Análise exploratória de dados
- ✅ Credenciais protegidas com variáveis de ambiente

## 🚀 Configuração Inicial

### Pré-requisitos

- Python 3.8 ou superior
- Conta no Reddit
- Credenciais da Reddit API ([Como obter](https://www.reddit.com/prefs/apps))

### 1. Clone o repositório

```bash
git clone <url-do-repositorio>
cd WebScrapping
```

### 2. Crie um ambiente virtual

```bash
python3 -m venv .venv
source .venv/bin/activate  # Linux/Mac
# ou
.venv\Scripts\activate  # Windows
```

### 3. Instale as dependências

```bash
pip install -r requirements.txt
```

### 4. Configure as credenciais do Reddit

1. **Obtenha suas credenciais:**
   - Acesse https://www.reddit.com/prefs/apps
   - Clique em "Create App" ou "Create Another App"
   - Escolha "script"
   - Anote o `client_id` (abaixo do nome) e `client_secret`

2. **Configure o arquivo .env:**

   ```bash
   cp .env.example .env
   ```

3. **Edite o arquivo .env** com suas credenciais:
   ```bash
   REDDIT_CLIENT_ID=seu_client_id_aqui
   REDDIT_CLIENT_SECRET=seu_client_secret_aqui
   REDDIT_USER_AGENT=seu_nome_ou_projeto
   ```

## 📦 Dependências Principais

- **pandas** - Manipulação e análise de dados
- **praw** - Python Reddit API Wrapper
- **selenium** - Automação web (se necessário)
- **python-dotenv** - Gerenciamento de variáveis de ambiente
- **openpyxl** - Suporte para exportação Excel
- **jupyter** - Notebooks interativos

## 🏃 Como Executar

### Opção 1: Jupyter Notebook (Recomendado)

1. Ative o ambiente virtual:

   ```bash
   source .venv/bin/activate
   ```

2. Abra o Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

3. Navegue até `Scraping.ipynb` e execute as células em ordem

### Opção 2: Script Python

```bash
python src/scraper.py  # (se disponível)
```

## 📁 Estrutura do Projeto

```
WebScrapping/
├── Scraping.ipynb         # Notebook principal de scraping
├── requirements.txt       # Dependências do projeto
├── .env                   # Credenciais (NÃO VERSIONAR!)
├── .env.example           # Template de credenciais
├── .gitignore            # Arquivos ignorados pelo Git
├── LICENSE               # Licença MIT
├── README.md             # Este arquivo
├── .venv/                # Ambiente virtual (não versionado)
├── learning-materials/   # Materiais de estudo (tutoriais, guias)
└── outputs/              # Arquivos Excel gerados (não versionado)
```

## 🔐 Segurança

### ⚠️ Nunca Commite:

- Arquivo `.env` com credenciais
- Arquivos com dados sensíveis
- API keys ou tokens
- Informações pessoais

### ✅ Boas Práticas:

- Use sempre variáveis de ambiente
- Mantenha o `.gitignore` atualizado
- Compartilhe apenas `.env.example`
- Revise commits antes de fazer push

## 📊 Dados Coletados

O projeto coleta as seguintes informações dos posts:

- **Title**: Título do post
- **Author**: Autor do post
- **Upvotes**: Número de upvotes
- **URL**: Link do post
- **Text**: Conteúdo do post (selftext)
- **Data/Hora**: Timestamp da coleta

## 🎯 Personalização

### Alterar Subreddit:

```python
# No notebook, célula de coleta
reddit.subreddit("nome_do_subreddit")
```

### Adicionar Filtros:

```python
# Modificar a lista de palavras-chave
key_words = ["palavra1", "palavra2", "palavra3"]
```

### Alterar Período:

```python
# time_filter: "hour", "day", "week", "month", "year", "all"
.top(time_filter="month", limit=100)
```

## 🐛 Troubleshooting

### Erro de autenticação

```
PRAWException: invalid_grant error processing request
```

**Solução:** Verifique se as credenciais no `.env` estão corretas.

### Erro de import do dotenv

```
ModuleNotFoundError: No module named 'dotenv'
```

**Solução:**

```bash
pip install python-dotenv
```

### Kernel não encontrado

**Solução:**

```bash
python -m ipykernel install --user --name=WebScraping
```

## 🤝 Contribuindo

Contribuições são bem-vindas! Para contribuir:

1. Fork o projeto
2. Crie uma branch para sua feature (`git checkout -b feature/NovaFeature`)
3. Commit suas mudanças (`git commit -m 'feat: Adiciona nova feature'`)
4. Push para a branch (`git push origin feature/NovaFeature`)
5. Abra um Pull Request

## 📚 Recursos Úteis

- [PRAW Documentation](https://praw.readthedocs.io/)
- [Reddit API Rules](https://github.com/reddit-archive/reddit/wiki/API)
- [Pandas Documentation](https://pandas.pydata.org/docs/)
- [Python Dotenv](https://pypi.org/project/python-dotenv/)

## 🎓 Materiais de Aprendizado

A pasta `learning-materials/` contém tutoriais e guias sobre boas práticas de desenvolvimento Python:

- **Tutorial completo** de Jupyter Notebooks
- **Checklist** para novos projetos
- **Comandos úteis** (Git, Python, Jupyter)
- **Templates** de README para diferentes tipos de projeto
- **Guias** de deploy e configuração

Estes materiais são independentes deste projeto e podem ser usados para estudo e referência em outros projetos.

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo `LICENSE` para mais detalhes.

## 👤 Autor

**Gustavo Teixeira Bittenourt de Oliveira**

- User Agent: Gustavo
- Projeto: Web Scraping Reddit

---

**⭐ Se este projeto foi útil, considere dar uma estrela no GitHub!**

_Última atualização: Fevereiro 2026_
