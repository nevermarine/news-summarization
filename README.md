# Сервер для суммаризации новостей.

## Как запустить?
1. Установить [ollama](https://ollama.com/download)
2. Запустить ollama через `ollama serve` или через systemd-сервис
3. Скачать чекпоинт [Saiga-Mistral 7b](https://huggingface.co/IlyaGusev/saiga_mistral_7b_gguf) ([конкретно файл model-q4_K.gguf](https://huggingface.co/IlyaGusev/saiga_mistral_7b_gguf/resolve/main/model-q4_K.gguf?download=true)) и поместить его в папку этого репозитория
4. Добавить модель командой `ollama create summarization -f ./Modelfile`
5. Теперь можно выполнять к этой модели реквесты, используя [ollama API](https://github.com/ollama/ollama/blob/main/docs/api.md). Пример json с запросом лежит в файле `test-request.json`. Пример курла: 
```
curl http://localhost:11434/api/generate -d @test-request.json
```