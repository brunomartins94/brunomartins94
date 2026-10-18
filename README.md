# Bruno Martins | Desenvolvimento de Software, Games e Engenharia de Dados

Atuo em três frentes:

- **Desenvolvimento de software:** sistemas, aplicativos, sites e integrações para diferentes necessidades.
- **Desenvolvimento de games:** jogos autorais, mecânicas, interfaces, adversários e progressão.
- **Engenharia de dados:** pipelines, modelagem, automação e qualidade de dados.

Cada área tem seus próprios projetos e desafios. Aqui compartilho código, decisões técnicas e resultados.

**Tecnologias:** JavaScript, HTML, CSS, Canvas, Python, SQL, dbt, Apache Airflow, DuckDB, PostgreSQL, Docker e GitHub Actions.

## Sistemas, aplicativos e sites

Desenvolvo soluções de software, da interface às regras e integrações necessárias para o produto funcionar.

- <a href="https://brunomartins94.github.io/personal_site/" target="_blank" rel="noopener noreferrer">Site principal</a>: apresentação profissional, projetos e jogos disponíveis para jogar no navegador.
- <a href="https://brunomartins94.github.io/" target="_blank" rel="noopener noreferrer">Blog técnico</a>: notas técnicas e artigos sobre projetos e decisões de desenvolvimento de software, games e engenharia de dados.

## Engenharia de dados — projetos em destaque

### [Public API to S3 Landing Zone](https://github.com/brunomartins94/public-api-s3-landing)

Landing zone incremental para uma API pública, com persistência de dados brutos no Amazon S3 antes de qualquer transformação.

- Extrai uma API paginada com **Python, Requests e Boto3**.
- Grava JSON particionado por data de ingestão e página.
- Evita duplicação em reexecuções com chaves determinísticas.
- Provisiona S3 privado, criptografado e versionado com **Terraform**.
- Executa pipeline, testes, AWS CLI e Terraform com **Docker Compose**.

📚 [Nota técnica: da API pública ao S3](https://brunomartins94.github.io/notas/api-s3-landing-zone/)

### [S3 Raw JSON to Parquet](https://github.com/brunomartins94/s3-raw-to-parquet)

Transformação da camada raw em JSON para Parquet particionado, criada para diminuir o volume de armazenamento e permitir consultas analíticas sobre dados já preservados no S3.

- Lê dados raw no **Amazon S3** e valida um esquema explícito com **PyArrow**.
- Grava Parquet comprimido e particionado por data de ingestão.
- Consulta o resultado com **DuckDB**, sem nova chamada à API de origem.
- Demonstrou redução de **79,12%**: 44.708 bytes de JSON para 9.333 bytes de Parquet.
- Impede uma nova gravação quando o arquivo da data já existe.

📚 [Nota técnica: do JSON bruto ao Parquet](https://brunomartins94.github.io/notas/s3-raw-json-para-parquet/)

### [Parquet to Star Schema](https://github.com/brunomartins94/parquet-to-star-schema)

Modelo dimensional construído sobre a camada Parquet para dar uma definição comum a métricas de cobertura, categoria, localização e status.

- Modela `dim_date`, `dim_brewery`, `dim_brewery_type`, `dim_location` e `fact_brewery_snapshot`.
- Documenta o grão da fato: uma cervejaria observada por data de ingestão.
- Cria marts em Parquet no **Amazon S3** e consulta as relações com **DuckDB**.
- Processou **100 registros**, incluindo **58** microcervejarias, **26** brewpubs e **4** registros encerrados.
- Valida transformação e consulta com **3 testes no Docker**.

📚 [Nota técnica: do Parquet ao modelo estrela](https://brunomartins94.github.io/notas/parquet-para-modelo-estrela/)

### [Observatório Eleitoral 2026](https://github.com/brunomartins94/observatorio-eleitoral-2026)

Pipeline end-to-end de dados públicos do TSE para análise eleitoral brasileira.

- Processa **1.044.734 candidaturas** de 2018, 2022 e 2024.
- Consolida cerca de **11 milhões de registros** de candidaturas, receitas e despesas.
- Usa **Airflow, MinIO, DuckDB, dbt, Streamlit, Docker e GitHub Actions**.
- Produz datasets analíticos para responder perguntas sobre candidaturas, financiamento e representatividade.

> Um bom pipeline não termina ao carregar os dados: ele deixa claro de onde vieram, como foram transformados e se ainda podem ser confiados.

## Práticas em engenharia de dados

| Camada | Práticas e ferramentas |
| --- | --- |
| Ingestão e modelagem | Python, APIs, arquivos públicos, SQL e modelagem dimensional |
| Automação | Apache Airflow, tarefas idempotentes, retries e dependências explícitas |
| Qualidade | Testes dbt, validações de esquema, métricas de completude e documentação |
| Entrega | Docker, GitHub Actions, dashboards e datasets voltados ao consumidor |

## Desenvolvimento de games

Desenvolvo games como uma área própria de atuação. Crio experiências para navegador, trabalhando em regras, controles, adversários, progressão e apresentação visual.

### <a href="https://brunomartins94.github.io/personal_site/jogos/orbital/" target="_blank" rel="noopener noreferrer">Jogar Orbital.io</a>

Arena espacial single player para navegador: colete recursos, cresça e dispute espaço com nove bots. Todos começam com zero pontos e a dificuldade altera o comportamento dos adversários.

- Canvas nativo, JavaScript e simulação local em Web Worker, sem servidor multiplayer.
- Três dificuldades, colisões, power-ups, skins e suporte a múltiplos idiomas.
- Interface responsiva para mouse e toque.

### <a href="https://brunomartins94.github.io/personal_site/jogos/primal-clash/" target="_blank" rel="noopener noreferrer">Jogar Primal Clash</a>

Campanha de estratégia em tempo real para navegador, baseada em recrutamento de tropas, gestão de recursos e progressão por fases.

- JavaScript sem framework de produção e execução inteiramente no navegador.
- Cinco fases, melhorias permanentes, dificuldades e progresso salvo localmente.
- Regras de combate e progressão cobertas por testes automatizados.

Os games têm seus próprios objetivos de jogabilidade e experiência, com projetos apresentados nesta seção.

## Contato

Projetos de sistemas, apps, sites, games e engenharia de dados.

<a href="https://www.linkedin.com/in/bruno-martins-a6289212b/" target="_blank" rel="noopener noreferrer">LinkedIn</a>
