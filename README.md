# building-with-claude-api

Notebooks com os exemplos do curso **Building with Claude API**, da Anthropic.

## Conteúdo

| Pasta | Descrição |
| --- | --- |
| [accessing-claude-with-api/](accessing-claude-with-api/) | Módulo 1: requisições, conversas multi-turn, system prompts, temperature, streaming e dados estruturados ([accessing-claude-with-api.ipynb](accessing-claude-with-api/accessing-claude-with-api.ipynb)) |

## Pré-requisitos

- **Python 3.13** (o notebook foi executado com a versão 3.13.3)
- **VS Code** com as extensões **Python** e **Jupyter** (ou outro ambiente que rode notebooks Jupyter)
- Uma **chave de API da Anthropic**, criada em [console.anthropic.com](https://console.anthropic.com/)

## Instalação

### 1. Criar e ativar um ambiente virtual (recomendado)

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
```

No Linux/macOS: `source .venv/bin/activate`.

### 2. Instalar as dependências

```bash
pip install "anthropic<1" python-dotenv ipykernel
```

| Pacote | Para que serve |
| --- | --- |
| `anthropic<1` | SDK Python da API do Claude. A versão é fixada abaixo de 1 porque o notebook usa o parâmetro `temperature`, que deixou de funcionar nas versões mais novas do SDK. |
| `python-dotenv` | Carrega a chave de API a partir do arquivo `.env` (`load_dotenv()`). |
| `ipykernel` | Permite que o Jupyter/VS Code use o ambiente virtual como kernel do notebook. |

### 3. Configurar a chave de API

Crie um arquivo `.env` dentro da pasta do notebook (por exemplo, `accessing-claude-with-api/.env`):

```env
ANTHROPIC_API_KEY=sua-chave-aqui
```

> O `.env` já está no `.gitignore`. Nunca faça commit da sua chave de API.

O arquivo [.vscode/settings.json](accessing-claude-with-api/.vscode/settings.json) contém `"python.terminal.useEnvFile": true`, que faz o VS Code carregar o `.env` também nos terminais Python.

## Executando o notebook

1. Abra [accessing-claude-with-api/accessing-claude-with-api.ipynb](accessing-claude-with-api/accessing-claude-with-api.ipynb) no VS Code.
2. Em **Select Kernel**, escolha o interpretador do ambiente virtual (`.venv`).
3. Execute a célula **Setup** primeiro e depois as demais, em ordem.

O notebook usa o modelo `claude-haiku-4-5`, definido na variável `model` da célula de setup.
