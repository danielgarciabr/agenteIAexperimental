# Projeto de Agentes de IA com Gemini, ADK e Python

Este projeto demonstra a criação de múltiplos agentes de inteligência artificial utilizando o modelo Gemini, o SDK de Agentes (ADK) e a linguagem de programação Python. O objetivo é explorar como diferentes agentes podem colaborar para realizar tarefas específicas, neste caso, desde a busca por notícias relevantes até a criação e revisão de um post para redes sociais.

## Visão Geral dos Agentes

Este projeto é composto por 4 agentes distintos, cada um com uma função específica:

### Agente 1: Buscador de Notícias

* **Configuração:** Assistente de pesquisa focado em identificar lançamentos recentes e relevantes.
* **Tarefa:** Utiliza a ferramenta de busca do Google (`google_search`) para recuperar as últimas notícias sobre um tópico específico.
* **Critérios de Relevância:** Prioriza um máximo de 5 lançamentos com base na quantidade e no entusiasmo das notícias. Lançamentos com pouca cobertura ou baixo entusiasmo podem ser substituídos por outros mais relevantes.
* **Temporalidade:** Os lançamentos relevantes devem ser atuais, com no máximo um mês de antiguidade em relação à data de hoje (18 de maio de 2025).

### Agente 2: Planejador de Posts

* **Configuração:** Planejador de conteúdo, especialista em redes sociais.
* **Tarefa:** Com base na lista de lançamentos mais recentes e relevantes fornecida pelo Buscador de Notícias, utiliza a ferramenta de busca do Google (`google_search`) para:
    * Identificar os pontos mais relevantes que poderiam ser abordados em um post sobre cada lançamento.
    * Buscar informações adicionais para aprofundar o conhecimento sobre os temas.
* **Resultado:** Escolhe o tema mais relevante com base nas pesquisas, retornando esse tema, seus pontos mais importantes e um plano com os assuntos a serem abordados no post a ser escrito posteriormente.

### Agente 3: Redator do Post

* **Configuração:** Redator Criativo especializado em criar posts virais para redes sociais.
* **Tarefa:** Utiliza o tema e os pontos mais relevantes fornecidos pelo Planejador de Posts para escrever um rascunho de post para Instagram sobre o tema indicado. O post deve ser engajador, informativo, com linguagem simples e incluir de 2 a 4 hashtags no final. O público-alvo é a comunidade da Alura, a maior escola online de tecnologia do Brasil.

### Agente 4: Revisor de Qualidade

* **Configuração:** Editor e Revisor de Conteúdo meticuloso, especializado em posts para redes sociais, com foco no Instagram.
* **Tarefa:** Revisa o rascunho de post de Instagram fornecido pelo Redator do Post, verificando clareza, concisão, correção e tom de escrita adequado para um público jovem entre 18 e 30 anos.
* **Resultado:** Se o rascunho estiver bom, responde apenas "O rascunho está ótimo e pronto para publicar!". Caso haja problemas, aponta-os e sugere melhorias.

## Tecnologias Utilizadas

* **Gemini:** O modelo de linguagem avançado do Google utilizado para as capacidades dos agentes.
* **Agent Development Kit (ADK):** O SDK que facilita a criação e o gerenciamento de agentes de IA.
* **Python:** A linguagem de programação principal para o desenvolvimento dos agentes e a integração com o Gemini e o ADK.
* **Google Search (via `google_search` tool):** Ferramenta utilizada pelos Agentes 1 e 2 para buscar informações na web.

## Pré-requisitos

Antes de executar este projeto, você precisará ter:

* **Python 3.x** instalado em seu sistema. Você pode baixá-lo em [https://www.python.org/downloads/](https://www.python.org/downloads/).
* Uma **conta no Google Cloud Platform** com o modelo Gemini habilitado e as permissões configuradas para utilizar o ADK.
* As **bibliotecas Python necessárias** instaladas. Você pode instalá-las usando o `pip`:

    ```bash
    pip install google-generativeai google-ai-platform google-cloud-ai-agents
    # Outras bibliotecas que você possa estar usando, como a ferramenta de busca
    # Se a ferramenta de busca for uma biblioteca separada, adicione a instalação aqui.
    # Exemplo: pip install google-api-python-client
    ```

## Como Executar o Projeto

1.  **Clone este repositório:**

    ```bash
    git clone [https://docs.github.com/en/repositories/archiving-a-github-repository/referencing-and-citing-content](https://docs.github.com/en/repositories/archiving-a-github-repository/referencing-and-citing-content)
    cd agenteIAexperimental
    ```

2.  **Configure as credenciais do Google Cloud:** Certifique-se de que suas credenciais para acessar o Gemini e o ADK estejam corretamente configuradas em seu ambiente (por exemplo, através de variáveis de ambiente, um arquivo de credenciais ou utilizando o Google Cloud CLI). Consulte a documentação do Google Cloud AI Platform Agents para obter mais detalhes sobre como configurar as credenciais.

3.  **Execute os scripts dos agentes:** Navegue até o diretório onde os scripts dos seus agentes estão localizados e execute-os usando o Python. Por exemplo:

    ```bash
    python agentes/agente_buscador_noticias.py
    python agentes/agente_planejador_posts.py
    python agentes/agente_redator_post.py
    python agentes/agente_revisor_qualidade.py
    ```

## Estrutura do Projeto

```
seu_projeto/
├── agentes/
│   ├── agente_buscador_noticias.py
│   ├── agente_planejador_posts.py
│   ├── agente_redator_post.py
│   ├── agente_revisor_qualidade.py
├── README.md
├── requirements.txt  # (Opcional: lista de dependências)
└── ... (outros arquivos do projeto)
```

## Próximos Passos e Melhorias

* Implementar um sistema de comunicação mais robusto e automatizado entre os agentes.
* Adicionar tratamento de erros e logs para monitorar o funcionamento dos agentes.
* Explorar diferentes configurações e parâmetros para otimizar o desempenho de cada agente.
* Integrar a capacidade de publicar o post revisado diretamente em uma plataforma de mídia social (com as devidas permissões e APIs).
* Adicionar testes unitários para garantir a qualidade e a confiabilidade do código dos agentes.
* Considerar a criação de uma interface de usuário simples para interagir com o fluxo de trabalho dos agentes.

## Contribuição

Pull requests são bem-vindos. Por favor, descreva claramente a mudança proposta e sua justificativa. Sinta-se à vontade para abrir issues para discutir melhorias ou relatar problemas.

## Licença
(https://opensource.org/licenses/MIT)
