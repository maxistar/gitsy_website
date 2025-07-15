---
layout: ../../layouts/MarkdownLayout.astro
title: Создание приватного репозитория GitLab и настройка HTTPS-доступа
---




## Создание приватного репозитория

1. Перейдите на [GitLab](https://gitlab.com) и войдите в свой аккаунт
2. Нажмите кнопку "+" в верхней панели навигации и выберите "New project"
3. Введите имя проекта и описание
4. Выберите "Private" в разделе "Visibility Level"
5. Нажмите "Create project"

## Настройка HTTPS-доступа

1. Создание токена доступа:
   - Нажмите на вашу аватарку в правом верхнем углу
   - Перейдите в "Preferences"
   - В левой боковой панели нажмите "Access Tokens"
   - Введите имя для токена (например, "HTTPS Access")
   - Выберите "read_repository" и "write_repository" scopes
   - Нажмите "Create personal access token"
   - Сразу же скопируйте сгенерированный токен (вы не сможете увидеть его повторно)

2. Использование токена для HTTPS-доступа:
   - При клонировании или отправке в репозиторий используйте следующий формат:

   ```bash
   https://YOUR_USERNAME:YOUR_TOKEN@gitlab.com/YOUR_USERNAME/YOUR_PROJECT.git
   ```

   - Замените:
     - `YOUR_USERNAME` на ваше имя пользователя GitLab
     - `YOUR_TOKEN` на ваш токен доступа
     - `YOUR_PROJECT` на имя вашего проекта

## Важные замечания

- Храните ваш Токен доступа в безопасности и никогда не передавайте его
- Токен имеет доступ к вашим репозиториям в соответствии с выбранными правами доступа
- Вы можете отозвать токены в любое время в настройках GitLab
- Рекомендуется использовать менеджер паролей для безопасного хранения токена
- Токены GitLab истекают через 1 год по умолчанию

## Примеры команд

- Клонирование репозитория:

```bash
git clone https://YOUR_USERNAME:YOUR_TOKEN@gitlab.com/YOUR_USERNAME/YOUR_PROJECT.git
```

- Отправка в репозиторий:

```bash
git push https://YOUR_USERNAME:YOUR_TOKEN@gitlab.com/YOUR_USERNAME/YOUR_PROJECT.git
```
