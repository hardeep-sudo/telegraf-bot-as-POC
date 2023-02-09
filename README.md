# telegraf-bot-as-POC
<header>

<div align="center">
<img src="docs/assets/logo.svg" alt="logo" height="90" align="center">
<h1 align="center">index.js</h1>

<p>Modern Telegram Bot API framework for Node.js</p>

<a href="https://core.telegram.org/bots/api">
	<img src="https://img.shields.io/badge/Bot%20API-v6.3-f36caf.svg?style=flat-square" alt="Bot API Version" />
</a>
<a href="https://packagephobia.com/result?p=telegraf,node-telegram-bot-api">
	<img src="https://flat.badgen.net/packagephobia/install/telegraf" alt="install size" />
</a>
<a href="https://github.com/telegraf/telegraf">
	<img src="https://img.shields.io/github/languages/top/telegraf/telegraf?style=flat-square&logo=github" alt="GitHub top language" />
</a>
<a href="https://telegram.me/TelegrafJSChat">
	<img src="https://img.shields.io/badge/English%20chat-grey?style=flat-square&logo=telegram" alt="English chat" />
</a>
</div>

</header>

## For 3.x users

- [3.x docs](https://telegraf.js.org/v3)
- [4.0 release notes](https://github.com/telegraf/telegraf/releases/tag/v4.0.0)

## Introduction

Bots are special [Telegram](https://telegram.org) accounts designed to handle messages automatically.
Users can interact with bots by sending them command messages in private or group chats.
These accounts serve as an interface for code running somewhere on your server.

Telegraf is a library that makes it simple for you to develop your own Telegram bots using JavaScript or [TypeScript](https://www.typescriptlang.org/).

### Features

- Full support
- Excellent TypeScript typings
- Lightweight
- Compatible Webhooks
- Extensible

### Example

```js
const { Telegraf } = require('telegraf');
const { message } = require('telegraf/filters');

const bot = new Telegraf(process.env.BOT_TOKEN);
bot.start((ctx) => ctx.reply('Welcome'));
bot.help((ctx) => ctx.reply('Send me a sticker'));
bot.on(message('sticker'), (ctx) => ctx.reply('👍'));
bot.hears('hi', (ctx) => ctx.reply('Hey there'));
bot.launch();

// Enable graceful stop
process.once('SIGINT', () => bot.stop('SIGINT'));
process.once('SIGTERM', () => bot.stop('SIGTERM'));
```

```js
const { Telegraf } = require('telegraf');

const bot = new Telegraf(process.env.BOT_TOKEN);
bot.command('oldschool', (ctx) => ctx.reply('Hello'));
bot.command('hipster', Telegraf.reply('λ'));
bot.launch();

// Enable graceful stop
process.once('SIGINT', () => bot.stop('SIGINT'));
process.once('SIGTERM', () => bot.stop('SIGTERM'));
```

## Getting started

### Telegram token

To use the [Telegram Bot API](https://core.telegram.org/bots/api),
you first have to [get a bot account](https://core.telegram.org/bots)
by [chatting with BotFather](https://core.telegram.org/bots#6-botfather).

BotFather will give you a *token*, something like `123456789:AbCdefGhIJKlmNoPQRsTUVwxyZ`.

### Installation

```shellscript
$ npm install telegraf
```
or
```shellscript
$ yarn add telegraf
```
or
```shellscript
$ pnpm add telegraf
```

### `Telegraf` class

[`Telegraf`] instance represents your bot. It's responsible for obtaining updates and passing them to your handlers.

Start by [listening to commands](https://telegraf.js.org/classes/Telegraf-1.html#command) and [launching](https://telegraf.js.org/classes/Telegraf-1.html#launch) your bot.

### `Context` class

`ctx` you can see in every example is a [`Context`] instance.
[`Telegraf`] creates one for each incoming update and passes it to your middleware.
It contains the `update`, `botInfo`, and `telegram` for making arbitrary Bot API requests,
as well as shorthand methods and getters.

This is probably the class you'll be using the most. As it shown in above example

For Further ### Refrences

- [Getting started](#getting-started)
- [API reference](https://telegraf.js.org/modules.html)
- Telegram groups (sorted by number of members):
  * [English](https://t.me/TelegrafJSChat)
  * [Russian](https://t.me/telegrafjs_ru)
  * [Uzbek](https://t.me/botjs_uz)
  * [Ethiopian](https://t.me/telegraf_et)
- [GitHub Discussions](https://github.com/telegraf/telegraf/discussions)
- [Dependent repositories](https://libraries.io/npm/telegraf/dependent_repositories)

For additional bot examples please check the new [`docs repo`](https://github.com/feathers-studio/telegraf-docs/).

```
