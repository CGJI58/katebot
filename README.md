# katebot

케이트(katebot)는 개인 프로젝트로 운영되는 뉴스 검증 도구의 봇입니다. · katebot is the fetcher of a personal news-verification tool.

## 무엇을 하나요 (한국어)

케이트가 하는 일은 하나뿐입니다.

- 검증하는 사람이 기사 하나를 검증하다가 「원문에서 읽어 오기」 단추를 누를 때, **그 기사 페이지 한 건**만 가져옵니다. 사이트를 돌아다니며 모으거나(크롤) 링크를 따라가지 않고, 저절로 다시 가져오지 않습니다.
- 가져온 페이지에서는 언론사가 심어 둔 메타데이터(제목 · 언론사 · 기자 · 보도 일시)만 읽습니다. 페이지도 읽은 값도 저장하지 않습니다.
- 가져오기 전에 그 사이트의 robots.txt를 읽고, `katebot`이나 모든 봇(`*`)에게 막힌 페이지는 가져오지 않습니다.

## What does it do? (English)

katebot does exactly one thing.

- When a person verifying an article presses the "read from the original" button, katebot fetches **that single article page** only. It does not crawl sites or follow links, and it never re-fetches on its own.
- From the fetched page it reads only the metadata the publisher embedded (headline, publisher, author, date published). Neither the page nor the values are stored.
- Before fetching, it reads the site's robots.txt and does not fetch pages disallowed for `katebot` or for all bots (`*`).

## User-Agent

```
katebot/0.1 (+https://github.com/CGJI58/katebot)
```

## 가져오기를 원치 않으시면 · Opt-out

robots.txt에 아래처럼 적으시면 케이트는 그 사이트의 페이지를 가져오지 않습니다. 그 밖의 연락은 이 저장소의 [Issues](../../issues)로 주세요.

If you do not want katebot to fetch your pages, add the lines below to your robots.txt and katebot will stop. For anything else, please open an issue in this repository.

```
User-agent: katebot
Disallow: /
```
