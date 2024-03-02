# 🤖 ChatGPT-Assistant
Помощник по разговорам ChatGPT, созданный на основе Streamlit, прост в использовании, его нелегко отключить, и он поддерживает следующие функции:
- Несколько окон чата
- Сохранение исторических разговоров
- Контекст чата по умолчанию 
- Настройка параметров модели
- Экспортировать разговоры в виде файлов Markdown.
- Голосовая связь ChatGPT (рекомендуется браузер Edge на компьютере)
## 🤩[Развернутый проект](https://puchb-gpt.streamlit.app/)
- Чтобы напрямую использовать развернутый проект, вы можете настроить ключ Openai в настройках веб-страницы. В настоящее время исторические разговоры не сохраняются. Он действителен только в текущем сеансе пользователя и не будет доступен другим.
- Разверните проект самостоятельно. После настройки Openai Key в «Секретах» исторические записи разговоров будут сохранены. На данный момент его необходимо настроить как частное приложение для создания личного помощника GPT.   

### навыки:
- Дважды щелкните страницу, чтобы напрямую найти поле ввода.
- Ctrl + Enter, чтобы быстро задать вопросы

# развертывать

## Развертывание Streamlit Cloud (рекомендуется)
Его легко и бесплатно развернуть, и его можно использовать без доступа к Интернету. Обратите внимание, что оно устанавливается как частное приложение.
Пожалуйста, обратитесь к [подробным инструкциям](https://github.com/PierXuY/ChatGPT-Assistant/blob/main/Tutorial.md), предоставленным [@Hannah11111](https://github.com/Hannah11111).
1. Создайте форк этого проекта в вашем личном репозитории Github.
2. Зарегистрируйте [учётную запись Streamlit Cloud](https://share.streamlit.io/) и подключитесь к Github.
3. Начните развертывание приложения. Подробную информацию можно найти в [официальном руководстве](https://docs.streamlit.io/streamlit-community-cloud/get-started).
4. Настройте Openai Key в секретах приложения. Конкретный формат см. на рисунке ниже:
<div style="display: flex;">
   <img src="https://github.com/PierXuY/ChatGPT-Assistant/blob/main/Figure/advanced-setting.png" alt="advanced-setting.png" style="flex: 1; ширина: 40 %;"/>
   <img src="https://github.com/PierXuY/ChatGPT-Assistant/blob/main/Figure/set-apikey.png" alt="set-apikey.png" style="flex: 1; ширина: 40 %;" />
</div>
Вы также можете настроить его после завершения развертывания.

## Локальное развертывание
1. Создайте виртуальную среду (рекомендуется)

2. Клонируйте проект (вы также можете загрузить его локально вручную).
```bash
git clone https://github.com/PierXuY/ChatGPT-Assistant.git
```

3.Установить зависимости
```bash
pip install -r requirements.txt
```

4. Установить ключ API; Установить базу API (необязательно).）

- существовать `.streamlit/secrets.toml`записать в файл`apikey = "Openai Key"`
- существовать `.streamlit/secrets.toml`Запись прокси-интерфейса в файле может обеспечить научное использование, а формат:`apibase = "адрес прокси-интерфейса"`，описано следующим образом：   
  1. описано следующим образом[openai-forward](https://github.com/beidongjiedeguang/openai-forward)Установленный прокси-интерфейс`apibase = "https://api.openai-forward.com/v1"` 。
  2. Можно ссылаться[openai-forward](https://github.com/beidongjiedeguang/openai-forward)Проект строит собственный прокси-интерфейс и настраивает его.

5. Запустить приложение
```bash
streamlit run app.py
```

# иллюстрировать
- Имя пользователя и аватар в формате SVG можно настроить в файле [custom.py](https://github.com/PierXuY/ChatGPT-Assistant/blob/main/libs/custom.py) [(source)](https ://www.dicebear.com/playground?style=identicon).
- Отредактируйте [set_context.py](https://github.com/PierXuY/ChatGPT-Assistant/blob/main/libs/set_context.py) в развернутом исходном коде проекта, чтобы добавить предустановленные параметры контекста, которые будут автоматически синхронизироваться с приложением. .
- Если у вас есть условия, вы можете рассмотреть возможность изменения логики чтения и записи файлов в [helper.py](https://github.com/PierXuY/ChatGPT-Assistant/blob/main/libs/helper.py) на облачную базу данных. операции по предотвращению потери истории записей.


# Благодарности
- Самая ранняя модификация была основана на проекте [shan-mx/ChatGPT_Streamlit](https://github.com/shan-mx/ChatGPT_Streamlit), спасибо.
- На [Контекстную функцию] по умолчанию (https://github.com/PierXuY/ChatGPT-Assistant/blob/main/set_context.py) есть ссылка из [binary-husky/chatgpt_academic] (https://github.com/binary- husky/chatgpt_academic) и проект [f/awesome-chatgpt-prompts](https://github.com/f/awesome-chatgpt-prompts), спасибо.
- Функция голосового взаимодействия относится к проектам [talk-to-chatgpt](https://github.com/C-Nedelcu/talk-to-chatgpt) и [Голосовое управление для ChatGPT](https://chrome.google. com/webstore/detail/voice-control-for-chatgpt/eollffkcakegifhacjnlngohfdlidhn) реализация, спасибо.
- Местная функция научного доступа в Интернет может использовать проект [openai-forward](https://github.com/beidongjiedeguang/openai-forward), спасибо.
