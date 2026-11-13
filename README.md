# Anonymous Chat Bot (@HamdamNashnasBot)

An asynchronous bot for anonymous messaging between users, with user profiles, settings and an optional compatibility feature. It exists in two builds: one for **Telegram** and one for **Bale** (an Iranian messaging platform).

> The source code of this project is private. This page describes what it does and how it is built.

Try it: **@HamdamNashnasBot** on both Telegram and Bale.

## What it does
- **Anonymous messaging** between users.
- **User profiles** and per-user **settings**.
- **Compatibility feature** that can be switched on or off by a configuration flag, with no code change.
- **Required-subscription check:** a middleware that can require users to join a channel before using the bot.

## How it is built
- **aiogram** (async) with modular routers for start, profile, settings, compatibility and anonymous messaging. The anonymous handler is registered last so commands and menus take priority.
- **SQLAlchemy 2 async** with a session pool injected into every handler through middleware. Tables are created automatically on startup.
- **Platform adapters:** the Bale build points the same aiogram code at Bale's Bot API server, and handles features Bale lacks, such as webhook deletion, without crashing. Message formatting is switched between HTML (Telegram) and Markdown (Bale).
- **Logging** with loguru, and configuration through environment variables (no secrets in code).

## Stack
Python, aiogram, SQLAlchemy (async), loguru, asyncio.

## Contact
Amir Hossein Fotoohi - ahfotoohi@gmail.com - [LinkedIn](https://linkedin.com/in/amir-hossein-fotoohi-411429390)
