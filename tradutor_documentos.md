# Tradutor de Documentos

Este script traduz documentos do Word (.docx) para o idioma desejado utilizando a API do Azure Translator.

## Notebook utilizando a api do Azure Translator

Nome: **dio_tradutor_azure_desafio_projeto_tradutor.ipynb** 

## Pré-requisitos

* **API Key do Azure Translator:** Você precisa de uma chave de assinatura para usar a API do Azure Translator. Obtenha uma chave gratuita em [https://azure.microsoft.com/en-us/services/cognitive-services/translator/](https://azure.microsoft.com/en-us/services/cognitive-services/translator/).
* **Endpoint da API do Azure Translator:** Você precisa do endpoint da API do Azure Translator para o seu recurso.
* **Localização da API do Azure Translator:** Você precisa da localização da API do Azure Translator para o seu recurso.

## Instalação

1. Instale as bibliotecas necessárias:
```bash
pip install requests python-docx
```

2. Configure as variáveis de ambiente:
* `azureSubscriptionKey`: A chave de assinatura do Azure Translator.
* `azureEndPoint`: O endpoint da API do Azure Translator.
* `azureLocation`: A localização da API do Azure Translator.

**Exemplo:**
```bash
!pip install requests python-docx
import os
from google.colab import userdata
userdata['azureSubscriptionKey'] = 'sua_chave_de_assinatura'
userdata['azureEndPoint'] = 'seu_endpoint'
userdata['azureLocation'] = 'sua_localização'
```

## Uso

1. Importe as funções do script.

2. Chame a função `translate_document()` com o caminho do arquivo do documento .docx como argumento.

**Exemplo:**
```python
from translator import translate_document

path = 'meu_documento.docx' 
path_translated = translate_document(path)
print(f'O documento traduzido foi salvo em: {path_translated}')
```

## Funções

### `translate_text(text, target_language)`

* **Parâmetros:**
    * `text`: O texto a ser traduzido.
    * `target_language`: O idioma de destino para a tradução.
* **Retorno:** O texto traduzido.

### `translate_document(path)`

* **Parâmetros:**
    * `path`: O caminho do arquivo do documento .docx.
* **Retorno:** O caminho do arquivo do documento traduzido.

## Notas

* O script traduz cada parágrafo do documento individualmente.
* O idioma de origem é definido como "en-us".
* O idioma de destino pode ser alterado na variável `target_language`.
* O script salva o documento traduzido com o sufixo `_` e o idioma de destino (por exemplo, `meu_documento_pt-br.docx`).

## Exemplo de utilização

```python
# Importar as funções
from translator import translate_document

# Caminho do arquivo do documento
path = 'meu_documento.docx'

# Traduzir o documento para o português do Brasil
path_translated = translate_document(path)

# Imprimir o caminho do arquivo do documento traduzido
print(f'O documento traduzido foi salvo em: {path_translated}')
```

### Texto gerado por IA e revisado por humano

