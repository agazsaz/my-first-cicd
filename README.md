# my-first-cicd
<img width="1317" height="286" alt="изображение" src="https://github.com/user-attachments/assets/0482ff7b-0eb2-401a-ac9c-36a47c7a69f2" />
# my-first-cicd

Лабораторная работа: первый Pipeline на CI в GitHub Actions.

## Цель

Настроить GitHub Actions так, чтобы workflow автоматически запускался при каждом пуше в репозиторий.

---

## 1. Структура репозитория

Создана папка `.github/workflows/` и файл `hello.yml`:

```
my-first-cicd/
├── .github/
│   └── workflows/
│       └── hello.yml
└── README.md
```

<img width="283" height="190" alt="изображение" src="https://github.com/user-attachments/assets/930110ce-de83-452e-b0ee-2c0a8a00d496" />


---

## 2. Файл `hello.yml`

```yaml
name: Мой первый workflow

on: [push]   # Запускать при каждом пуше

jobs:
  build:
    runs-on: ubuntu-latest   # Использовать последнюю версию Ubuntu
    steps:
      - name: Скачать код из репозитория
        uses: actions/checkout@v4   # Шаг 1: скачать код

      - name: Запустить команду
        run: echo "Привет, мир! Я только что запустил CI!"   # Шаг 2: echo
```

<img width="654" height="295" alt="изображение" src="https://github.com/user-attachments/assets/0ef0ed6b-ff9b-49c9-a076-27ba4fa96413" />


---

## 3. Локальные команды

```bash
mkdir -p .github/workflows
touch .github/workflows/hello.yml

git add .
git commit -m "Add hello workflow"
git push origin main
```
<img width="654" height="295" alt="изображение" src="https://github.com/user-attachments/assets/a179a04c-fc0c-43a4-a33b-fcd08607d908" />

---

## 4. Результат — успешный запуск в Actions

После пуша workflow запустился автоматически. Вкладка Actions показывает успешное выполнение:

[СКРИНШОТ: вкладка Actions — workflow "Мой первый workflow" со статусом Success и зелёной галочкой]

---

## 5. Лог выполнения

Внутри job `build` видно, что команда `echo` выполнилась и вывела приветствие:

<img width="1317" height="286" alt="изображение" src="https://github.com/user-attachments/assets/da1d417b-3e98-4a0f-87fc-0e6d8a536506" />


---

## 6. Список запусков

История запусков workflow — все с зелёным статусом:


<img width="1236" height="248" alt="изображение" src="https://github.com/user-attachments/assets/56c49185-d0d3-4a6d-8d5f-579da310e78e" />

---

## Вывод

GitHub Actions автоматически запускает workflow при каждом пуше в репозиторий. Пайплайн отработал успешно, CI настроен корректно. Все поставленные задачи выполнены.
```
