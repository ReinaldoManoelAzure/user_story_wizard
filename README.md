# Wizard de Histórias de Usuário (Streamlit + LangChain)

Este app em Streamlit ajuda a montar **histórias funcionais** com **padrão rígido**. Permite:
- Inserir **informações macro** do desenvolvimento.
- Fazer **upload de imagens** (com análise opcional via OpenAI Vision).
- Fazer **upload de arquivos** de apoio: **PDF, DOCX, TXT, MD**.
- Gerar a história pelo **LangChain** (se `OPENAI_API_KEY` estiver configurada) ou via **template rígido**.
- Exportar em **Markdown**, **DOCX** e **pacote .zip** com contexto e metadados.

## Rodando localmente

```bash
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
pip install -r requirements.txt
streamlit run streamlit_app.py
```

### Configuração de chave (opcional para LLM)

Crie `.streamlit/secrets.toml` (ou exporte como variável de ambiente):

```toml
OPENAI_API_KEY = "sua_chave_aqui"
```

No Windows PowerShell:
```powershell
$env:OPENAI_API_KEY="sua_chave_aqui"
```

## Observações
- Para análise de imagens com LLM, o app converte as imagens para **data URL** e envia ao modelo **gpt-4o-mini** via `langchain_openai`.
- Caso não configure a API, o app continua funcionando e monta a história com o **template rígido**.
