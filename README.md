# tgchannel2csv
Parse public telegram channel's posts from t.me/s/ link to CSV file. Good if you need to review your posts through time.

Final results contains:
1. post id in a format `<channel_name>/post_incremental_id`
2. datetime utc
3. Published date
4. Published time
5. Text of the post
6. Urls of media attached: they are store in on cell, but you could split them by pipe "|" character

## ☑️ How to use

1. Open https://tg2csv.vitaly-krenel.workers.dev/<channel name without @> e.g. https://tg2csv.vitaly-krenel.workers.dev/krenels
2. Wait up to 25 sec
3. CSV file should automatically start downloading after that

Right now I use free Cloudflare Worker, so it fetches up to 400-1000 posts. After testing, it seems that the number of posts depends on the size each post.

## ❤️‍🔥 Motivation

I'm developing my own Telegram channel t.me/krenels for a couple of years. 

What I did before was mostly writing content, no real work in distribution or promotion. Recent in May 2025 I once again decided to get back and continue the channel. Now I wanted to understand: what I'm writing about, who loves my content and how I could find more people like that.

For me it seemed hard to move, without realizing what exactly I've done so far. For that reason I needed to review posts, classify them, see what topics I double down on, etc.
Analytics tools seemed ignoring this "quality" based analysis, providing only stats and no writing insights.

So I made a first step to allow me to chat over my posts with ChatGPT. 

It might not be optimal - maybe theres better tools for doing that. I researched briefly and solely for about an hour and decided to quickly make a simple script.

## 💪 When tgchannel2csv is useful?

- ⚡️ You need to quickly and easily get your own posts in CSV format - for analysis with ChatGPT or new content generation.
- 😍 You don't want to issue apiId and apiHash - e.g. you don't want to risk you main account
- You want CSV and not JSON/HTML

Telegram Desktop has export, but it doesn't produce CSV AND occasionally it requires you to wait for security reasons up to 24 hours. 

## Alternatives
1. In case you already have a chat exported in HTML format - you could use [telegram export converter](https://github.com/gabekanegae/telegram-export-converter). Didn't try myself, but it seems a good option if you have whole lot of posts.

2. In case you have `apiId` and `apiHash` - you could use [telegram channel downloader](https://github.com/abhishekjnvk/telegram-channel-downloader). Didn't try myself - for some reason when I needed to do it, my.telegram.org/apps decided not to issue apiId and hash for me 🙂

## ❓How it works?

Review the src to see the script. It's a basic parser that relies on t.me/s/ fetching posts using `?before=` query. 
I've deployed the original to Cloudflare Workers using Wrangler. No UI as I didn't have much time.

## 🗺️ Potential ideas to develop the project
*If you want to have fan or maybe I come back here in the future.*

- [ ] Add ways to chat with ChatGPT immediately  
- [ ] Make text of the post more readable
- [ ] Classify posts into topics or build a graph of topics
- [ ] Understand who those people that view/love the specific topics
- [ ] Get potential good follow-ups on the old posts

## Author
You can find me https://t.me/krenels. I write mostly in Russian, but you could use translate to read my posts 😉
