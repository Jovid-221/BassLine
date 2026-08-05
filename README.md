# MusicStudioVisual (musicstudiovisual.tj)

Один файл (`index.html`) — весь сайт целиком. Не нужен ни бэкенд, ни база данных,
ни сборка (build). Просто статичный файл, который отдаёт любой хостинг как есть.

В архиве уже лежит файл `CNAME` с твоим доменом (`musicstudiovisual.tj`) —
GitHub Pages сам подхватит его и привяжет домен, ничего вручную вписывать
в репозитории не нужно.

---

## Шаг 1 — GitHub

1. Зайди на github.com → New repository → назови как хочешь (например `musicstudiovisual`).
2. Загрузи из этого архива **оба** файла — `index.html` и `CNAME` — в корень
   репозитория (Add file → Upload files).
3. Repository → Settings → Pages → в Source выбери **Deploy from a branch**,
   ветка `main`, папка `/root` → Save.
4. Через 1–2 минуты GitHub Pages поднимет сайт на временном адресе
   `https://<твой-логин>.github.io/...` — дальше настраиваем домен.

---

## Шаг 2 — Домен musicstudiovisual.tj

Раз домен уже куплен — переходим сразу к DNS.

---

## Шаг 3 — Cloudflare (DNS)

1. Cloudflare Dashboard → Add a site → впиши `musicstudiovisual.tj`.
2. Cloudflare покажет два свои nameserver-а — их нужно прописать у
   регистратора, где куплен домен (раздел обычно называется Nameservers / NS-записи).
3. В Cloudflare DNS добавь:
   - `CNAME` @ → `<твой-логин>.github.io`
   - `CNAME` www → `<твой-логин>.github.io`
   (галочку "Proxy" — оранжевое облако — можно оставить включённой)
4. Вернись в GitHub → Settings → Pages → в поле Custom domain впиши
   `musicstudiovisual.tj` → Save. GitHub сам проверит, что CNAME-файл и
   DNS совпадают, и включит HTTPS (обычно занимает до часа).

Всё, DNS обновляется от пары минут до пары часов.

---

## Важно

- Файл всё делает в браузере пользователя — ничего никуда не отправляется,
  бэкенд не нужен ни на каком из этих хостингов.
- Единственная внешняя зависимость — Google Fonts (шрифты подгружаются по
  интернету). Если хочешь совсем без внешних подключений — скажи, вырежу.
- Если позже захочешь переехать на Cloudflare Pages вместо GitHub Pages —
  файл `CNAME` для этого не нужен, домен там привязывается прямо в
  Cloudflare Dashboard (Workers & Pages → Custom domains).
