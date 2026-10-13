# my-first-cicd
<img width="1317" height="286" alt="изображение" src="https://github.com/user-attachments/assets/0482ff7b-0eb2-401a-ac9c-36a47c7a69f2" />
```yaml
name: Мой первый workflow
on: [push] # Запускать при каждом пуше

jobs:
  build:
    runs-on: ubuntu-latest # Использовать последнюю версию Ubuntu
    steps:
      - name: Скачать код из репозитория
        uses: actions/checkout@v4 # Шаг 1: инициализация и клонирование вашего кода на виртуальную машину
        
      - name: Запустить команду
        run: echo "Привет, мир! Я только что запустил CI!" # Шаг 2: выполнение bash-команды
```
