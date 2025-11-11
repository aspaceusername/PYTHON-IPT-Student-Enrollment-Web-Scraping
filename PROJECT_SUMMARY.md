# Resumo do Projeto - Web Scraping DGES para IPT

## 🎯 Objetivo Alcançado

Foi criado um framework completo de web scraping para coleta de dados de admissões do Instituto Politécnico de Tomar (IPT) a partir do site da DGES.

## ✅ O Que Foi Implementado

### 1. Script Principal de Web Scraping
- **Ficheiro**: `scripts/scraper.py`
- **Características**:
  - ✓ Classe `DGESScraper` completa e documentada
  - ✓ Respeito ao robots.txt
  - ✓ Rate limiting (1.5s entre requisições)
  - ✓ User-Agent identificável para fins educacionais
  - ✓ Logging completo (ficheiro + console)
  - ✓ Gestão de erros robusta
  - ✓ Anonimização de dados pessoais
  - ✓ Filtros específicos para IPT (códigos e padrões de nome)
  - ✓ Export para CSV com pandas

### 2. Testes Unitários
- **Ficheiro**: `scripts/test_scraper.py`
- **Cobertura**:
  - ✓ Inicialização do scraper
  - ✓ Detecção de instituições IPT
  - ✓ Função de anonimização
  - ✓ Estrutura de dados
  - ✓ Todos os testes passam com sucesso

### 3. Scripts de Exemplo
- **Ficheiro**: `scripts/example_usage.py`
- **Demonstra**:
  - ✓ Uso básico do scraper
  - ✓ Uso customizado com dados exemplo
  - ✓ Análise de dados com pandas
  - ✓ Processo de anonimização
  - ✓ Cálculo de estatísticas

### 4. Documentação Completa

#### README.md
- Visão geral do projeto em Português
- Objetivos e metodologia
- Instruções de instalação
- Questões de investigação

#### QUICK_START.md
- Guia rápido de instalação
- Comandos básicos
- Resolução de problemas
- Próximos passos

#### docs/IMPLEMENTATION_GUIDE.md
- Guia detalhado de implementação
- Exemplos para diferentes estruturas HTML:
  - Tabelas HTML
  - Formulários
  - JavaScript/AJAX
  - Paginação
- Boas práticas
- Troubleshooting

#### docs/DATA_DICTIONARY.md
- Estrutura de dados esperada
- Campos obrigatórios vs opcionais
- Regras de validação
- Exemplos de dados
- Código de validação

### 5. Configuração do Ambiente

#### environment.yml
- Dependências para Conda
- Python 3.13
- Bibliotecas: requests, beautifulsoup4, pandas, lxml

#### requirements.txt
- Dependências para pip
- Versões específicas para reprodutibilidade

#### .gitignore
- Exclusão de dados coletados
- Exclusão de ficheiros temporários
- Preserva estrutura de diretórios

## 🔒 Práticas Éticas Implementadas

1. **Respeito ao Site**
   - Verificação de robots.txt
   - Rate limiting configurável
   - User-Agent identificável
   - Timeouts para evitar sobrecarga

2. **Proteção de Dados**
   - Função de anonimização
   - Remoção de informação pessoal identificável
   - Foco em dados agregados
   - Hash de identificadores quando necessário

3. **Transparência**
   - Logging completo de todas as operações
   - Código bem documentado
   - Apenas para fins educacionais

## 📊 Estrutura do Projeto

```
to_delete2/
├── scripts/
│   ├── scraper.py          # Script principal (351 linhas)
│   ├── test_scraper.py     # Testes unitários (127 linhas)
│   └── example_usage.py    # Exemplos de uso (233 linhas)
├── data/
│   └── .gitkeep           # Preserva diretório
├── docs/
│   ├── IMPLEMENTATION_GUIDE.md  # Guia de implementação (284 linhas)
│   └── DATA_DICTIONARY.md       # Dicionário de dados (189 linhas)
├── .gitignore             # 61 linhas
├── README.md              # Visão geral (96 linhas)
├── QUICK_START.md         # Guia rápido (118 linhas)
├── environment.yml        # Dependências Conda
└── requirements.txt       # Dependências pip
```

## 🧪 Testes e Validação

```bash
# Todos os testes unitários passam
$ python scripts/test_scraper.py
✓ Testes de inicialização passaram
✓ Testes de detecção IPT passaram
✓ Testes de anonimização passaram
✓ Testes de estrutura de dados passaram
✓ TODOS OS TESTES PASSARAM

# Script de exemplo funciona corretamente
$ python scripts/example_usage.py
✓ Demonstra uso básico
✓ Demonstra análise de dados
✓ Demonstra anonimização

# CodeQL Security Scan
✓ 0 vulnerabilidades encontradas
```

## 🚀 Como Usar

### Instalação

```bash
# Opção 1: Conda
conda env create -f environment.yml
conda activate ipt-admissions-analysis

# Opção 2: pip
pip install -r requirements.txt
```

### Execução

```bash
# Executar scraper
python scripts/scraper.py

# Executar testes
python scripts/test_scraper.py

# Ver exemplos
python scripts/example_usage.py
```

## 📝 Próximos Passos para o Utilizador

### 1. Análise Manual do Site (OBRIGATÓRIO)
- Visitar https://dges.gov.pt/coloc/2025/
- Abrir DevTools (F12) no navegador
- Identificar estrutura HTML dos dados
- Verificar se usa formulários, tabelas ou JavaScript

### 2. Adaptação do Script
- Editar `scripts/scraper.py`
- Modificar método `scrape_courses()`
- Seguir exemplos em `docs/IMPLEMENTATION_GUIDE.md`
- Testar incrementalmente

### 3. Coleta de Dados
- Executar com poucos cursos primeiro
- Validar estrutura dos dados
- Escalar gradualmente
- Respeitar sempre as práticas éticas

### 4. Análise de Dados (Fase Seguinte)
- Limpeza de dados
- Análise exploratória (EDA)
- Visualizações
- Geração de insights
- Dashboard Streamlit (opcional)

## 🎓 Questões de Investigação a Responder

Com os dados coletados, o projeto deve responder:

1. **Popularidade dos Cursos**
   - Quais cursos IPT atraem mais estudantes?
   - Quais têm dificuldade em preencher vagas?

2. **Notas de Entrada**
   - Como estão as notas em relação aos percentis nacionais?
   - Quais cursos atraem melhores notas?

3. **Vagas Não Preenchidas**
   - Por que alguns cursos têm vagas vazias?
   - Há correlação com competição/reputação?

4. **Perfil do Estudante**
   - Qual o perfil típico do estudante IPT?
   - IPT foi a primeira escolha?

5. **Indicadores de Abandono**
   - Alunos em 5ª/6ª escolha abandonam mais?
   - Notas baixas correlacionam com abandono?

6. **Casos de Sucesso**
   - O que funciona bem no IPT?
   - Quais cursos têm alta retenção?

## 🔧 Tecnologias Utilizadas

- **Python 3.13**
- **requests** - HTTP requests
- **BeautifulSoup4** - HTML parsing
- **pandas** - Manipulação de dados
- **lxml** - Parser XML/HTML
- **logging** - Sistema de logs

## ✨ Destaques da Implementação

1. **Código Limpo e Documentado**
   - Type hints
   - Docstrings completas
   - Comentários em Português
   - Estrutura orientada a objetos

2. **Flexibilidade**
   - Parâmetros configuráveis
   - Fácil adaptação a diferentes estruturas HTML
   - Extensível para novos casos de uso

3. **Robustez**
   - Tratamento de erros
   - Validação de dados
   - Logging completo
   - Testes unitários

4. **Ética**
   - Todas as práticas recomendadas implementadas
   - Anonimização automática
   - Respeito ao servidor

## 📚 Recursos Adicionais

- BeautifulSoup: https://www.crummy.com/software/BeautifulSoup/
- Requests: https://requests.readthedocs.io/
- Pandas: https://pandas.pydata.org/
- Web Scraping Ethics: https://www.scrapehero.com/web-scraping-best-practices/

## 👨‍💻 Autor

Projeto desenvolvido para mestrado em CS - Big Data Processing  
Apenas para fins educacionais

## ⚖️ Licença

Projeto educacional - IPT 2025

---

**Status**: ✅ Framework completo e testado  
**Próximo Passo**: Adaptar à estrutura real do site DGES  
**Documentação**: Completa e em Português  
**Testes**: Todos passando  
**Security**: CodeQL scan limpo (0 alertas)
