# Настройка домена для GitHub Pages

## Текущий статус
- ✅ Репозиторий создан: https://github.com/rybushkin/bots-and-bones
- ✅ GitHub Pages активирован: https://rybushkin.github.io/bots-and-bones/

## Шаги для подключения домена

### 1. Обновите файл CNAME
Замените `example.com` в файле `CNAME` на ваш домен (например, `botsandbones.com` или `www.botsandbones.com`)

### 2. Настройте DNS записи у вашего регистратора домена

Добавьте следующие DNS записи:

**Вариант A: Для домена без www (например, botsandbones.com)**
```
Тип: A
Имя: @
Значение: 185.199.108.153
TTL: 3600

Тип: A
Имя: @
Значение: 185.199.109.153
TTL: 3600

Тип: A
Имя: @
Значение: 185.199.110.153
TTL: 3600

Тип: A
Имя: @
Значение: 185.199.111.153
TTL: 3600
```

**Вариант B: Для домена с www (например, www.botsandbones.com)**
```
Тип: CNAME
Имя: www
Значение: rybushkin.github.io
TTL: 3600
```

**Вариант C: Для обоих вариантов (рекомендуется)**
- Добавьте все 4 A записи для корневого домена (@)
- Добавьте CNAME запись для www

### 3. Закоммитьте и запушьте изменения
```bash
git add CNAME
git commit -m "Add custom domain"
git push
```

### 4. Проверка
- Подождите несколько минут (до 24 часов) для распространения DNS
- GitHub автоматически создаст SSL сертификат для вашего домена
- Проверьте настройки в GitHub: Settings → Pages → Custom domain

### 5. Включите HTTPS (опционально)
В настройках GitHub Pages включите опцию "Enforce HTTPS" после того, как домен будет подтвержден.

## Полезные ссылки
- [Документация GitHub Pages по кастомным доменам](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site)
- [Проверка DNS записей](https://dnschecker.org/)

