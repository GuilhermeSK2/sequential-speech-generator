# Gerador de Discursos com Cadeias Sequenciais (LangChain & Streamlit)

Este projeto implementa um aplicativo web interativo que demonstra o poder das cadeias sequenciais do LangChain para gerar conteúdo de texto complexo em etapas. O aplicativo aceita um tópico do usuário e, em seguida, gera um título impactante para um discurso e, posteriormente, o discurso completo, tudo em um fluxo automatizado.

## Visão Geral

A geração de conteúdo de texto em múltiplas etapas, onde a saída de uma etapa serve como entrada para a próxima, é uma técnica poderosa em LLMs. Este projeto ilustra isso com o seguinte fluxo:

1.  **Entrada do Usuário:** O usuário fornece um `tópico` para o discurso através de uma interface Streamlit.
2.  **Primeira Cadeia (Geração de Título):** Uma `PromptTemplate` instrui o modelo Gemini (`gemini-2.5-flash`) a atuar como um "escritor de discursos experiente" e a gerar um **título único e impactante** com base no `tópico`. Um `StrOutputParser` garante que apenas a string do título seja retornada.
3.  **Segunda Cadeia (Geração de Discurso):** A saída da primeira cadeia (o título gerado) é passada como entrada para a segunda cadeia. Outra `PromptTemplate` instrui o modelo Gemini a escrever um **discurso de 350 palavras** com base nesse `título`.
4.  **Exibição da Resposta:** O discurso completo gerado é exibido na interface do Streamlit.

## Estrutura do Projeto

* `simple_sequential_chain_demo.py`: O script principal do aplicativo Streamlit.

## Tecnologias Utilizadas

* **Python 3**
* **Streamlit**: Para construir a interface web interativa.
* **LangChain Google Generative AI (`langchain_google_genai`)**: Para interagir com o modelo Gemini.
* **LangChain PromptTemplate**: Para criar prompts estruturados.
* **LangChain Core Output Parsers (`StrOutputParser`)**: Para formatar a saída da cadeia.
* **Google Gemini API**: Para o modelo de linguagem (`gemini-2.5-flash`).


## Uso do Aplicativo

Na interface do Streamlit, você encontrará um campo de texto para inserir o tópico do discurso. Digite o tópico desejado (ex: "Automobilismo") e, em seguida, o aplicativo gerará e exibirá o título e o discurso completo.

## Exemplo de uso:

<img width="791" height="861" alt="Image" src="https://github.com/user-attachments/assets/f2680ed0-720c-499a-8906-0844b299a7ca" />
