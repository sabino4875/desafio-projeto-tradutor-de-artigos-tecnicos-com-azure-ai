# Tradutor de Artigos

Este script extrai o texto de um artigo da web e o traduz para o idioma desejado usando o modelo de linguagem OpenAI Azure.

## Notebook utilizando a api do Azure Translator

Nome: [dio_tradutor_azure_desafio_projeto_tradutor_openai.ipynb](dio_tradutor_azure_desafio_projeto_tradutor_openai.ipynb) 

## Pré-requisitos

* **API Key do Azure OpenAI:** Você precisa de uma chave de assinatura para usar o Azure OpenAI. Obtenha uma chave gratuita em [https://azure.microsoft.com/en-us/products/cognitive-services/openai/](https://azure.microsoft.com/en-us/products/cognitive-services/openai/).
* **Endpoint da API do Azure OpenAI:** Você precisa do endpoint da API do Azure OpenAI para o seu recurso.
* **Nome do Deployment do Azure OpenAI:** Você precisa do nome do deployment do Azure OpenAI para o seu modelo.
* **Versão da API do Azure OpenAI:** Você precisa da versão da API do Azure OpenAI para o seu recurso.

## Instalação

1. Instale as bibliotecas necessárias:
```bash
!pip install requests beautifulsoup4 openai langchain-openai
```

2. Configure as variáveis de ambiente:
* `azureSubscriptionKey`: A chave de assinatura do Azure OpenAI.
* `azureEndPoint`: O endpoint da API do Azure OpenAI.
* `deploymentName`: O nome do deployment do Azure OpenAI.
* `apiVersion`: A versão da API do Azure OpenAI.

**Exemplo:**
```bash
!pip install requests beautifulsoup4 openai langchain-openai
import os
from google.colab import userdata
userdata['azureSubscriptionKey'] = 'sua_chave_de_assinatura'
userdata['azureEndPoint'] = 'seu_endpoint'
userdata['deploymentName'] = 'seu_nome_de_deployment'
userdata['apiVersion'] = 'sua_versao_da_api'
```

## Uso

1. Importe as funções do script.

2. Defina a URL do artigo que você deseja traduzir.

3. Chame a função `translate_article()` com o texto do artigo e o idioma de destino como argumentos.

**Exemplo:**
```python
from translator import translate_article, extract_text_from_url

# URL do artigo
url = "https://www.example.com/artigo"

# Extrair o texto do artigo
text = extract_text_from_url(url)

# Traduzir o artigo para o português do Brasil
article = translate_article(text, "pt-br")

# Imprimir o artigo traduzido
print(article)
```

## Funções

### `extract_text_from_url(url)`

* **Parâmetros:**
    * `url`: A URL do artigo.
* **Retorno:** O texto extraído do artigo.

### `translate_article(text, lang)`

* **Parâmetros:**
    * `text`: O texto do artigo.
    * `lang`: O idioma de destino para a tradução.
* **Retorno:** O artigo traduzido.

## Notas

* O script utiliza o modelo de linguagem OpenAI Azure para tradução.
* O idioma de destino pode ser qualquer idioma suportado pelo modelo de linguagem.
* O script formata a resposta do modelo de linguagem como markdown.

## Exemplo de utilização

```python
# Importar as funções
from translator import translate_article, extract_text_from_url

# URL do artigo
url = "https://www.example.com/artigo"

# Extrair o texto do artigo
text = extract_text_from_url(url)

# Traduzir o artigo para o português do Brasil
article = translate_article(text, "pt-br")

# Imprimir o artigo traduzido
print(article)
```

### Texto gerado por IA e revisado por humano
