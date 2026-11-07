# Telegram join request bot

How to approve Telegram join requests automatically, with a bot that also sends each new member one welcome message. This repository is a guide. It holds no code. The bot is Join Approve, [@JoinApproveProBot](https://t.me/JoinApproveProBot?start=github), and it runs on our side, so there is nothing to host.

## What a join request is

A join request is what Telegram creates when someone opens an invite link that has Request Admin Approval switched on. The person is not a member until an admin or a bot approves the request. The switch sits on the invite link, not on the channel, so one channel can have an open link and a second link that sends requests.

With no bot, every request waits in the admin's list and someone has to tap Approve on each one. That is fine for a small channel. For a channel that gets hundreds of requests after one promoted post, it does not work, and people lose interest while they wait.

## Setup in three steps

1. Open [Join Approve](https://t.me/JoinApproveProBot?start=github) and press Start. The buttons there add the bot to a channel or to a group.
2. Make the bot an admin with the right to add members. Telegram calls it Invite users or Add members, depending on the app. Without it Telegram does not send the bot any requests.
3. Check that the invite link you share has Request Admin Approval switched on. To do that, open the channel info, then Manage Channel, then Invite Links, and create a new link with the switch on. Revoke the old open link if you want every new member to go through requests.

That is all. Send `/setup` to the bot in a private chat to see your chats, change the welcome text, switch the welcome off or pause approval.

## What the new member receives

The bot approves each request as it arrives. It then sends the person who asked to join one private message, once. Telegram lets a bot write to a requester for a short time only, so the message goes out within 5 minutes of the request. Nobody who did not ask to join gets anything.

On the free plan an English speaker sees this, with the name of your channel in place of the placeholder.

```
You're in {title}. 👋

ℹ️ One message only: you asked to join {title}.
Powered by @JoinApproveProBot
```

A button under it reads Auto-approve for your channel and opens the bot. The bot reads the language of the person's Telegram app and sends the text in one of 11 languages, with English as the fallback.

## The rate

Join Approve approves every request at once. It sends at most 20 welcome messages a minute for one chat. If more than 20 people arrive in the same minute, all of them are approved and only the welcome is skipped for the extra people. A channel that gets 600 requests an hour averages 10 a minute, so everyone is welcomed. A burst of 200 requests in two minutes approves all 200 and welcomes the first 20 in each minute.

A welcome can also be missing because the request was more than 5 minutes old when the bot got to it, or because you switched the welcome off. The request is approved in both cases.

## Free and Pro

| | Free | Pro |
|---|---|---|
| Approve every request | yes | yes |
| Welcome on, off or paused per chat | yes | yes |
| Welcome text | default | your own, up to 500 characters |
| Button under the welcome | the bot's | your own |
| Footer | shown | removed |
| Approval delay | none | 1, 5, 15 or 60 minutes |
| Stats | none | last 7 days |

Pro is per chat. It costs 150 Stars once, about $3. A chat with 500 or more members is offered 300 Stars per 30 days instead. You pay in a private chat with the bot, never in the channel. Once the bot has been in a chat for 24 hours, `/setup` offers one free 24 hour trial of Pro.

## FAQ

### Does it work for channels and for groups?

Yes, both. Add it as an admin with the right to add members, and it handles join requests for either.

### Can I switch the welcome message off?

Yes. Open `/setup` in a private chat with the bot, pick the chat and switch the welcome off. Requests are still approved.

### Does it screen people?

No. Every request is approved. If you want to look at each person, approve by hand.

### What happens at 500 members?

The free plan keeps working with no limit on approvals. From 500 members, the Pro offer for that chat becomes 300 Stars per 30 days instead of 150 Stars once. Nothing changes until you choose to pay.

### Why did a member get no welcome?

Either more than 20 people arrived in that minute, the request was older than 5 minutes when the bot read it, or the welcome is switched off. The request was approved all the same.

### Where is the code?

The bot is hosted, so there is none here. This repository is the written guide.

## More

- The bot, [@JoinApproveProBot](https://t.me/JoinApproveProBot?start=github)
- The longer guide, [Telegram channel join requests and auto approval](https://addthisbot.com/guides/telegram-channel-join-requests/)
- The bot page, [addthisbot.com/bots/approver](https://addthisbot.com/bots/approver/)
- Telegram on join requests, [core.telegram.org/api/invites](https://core.telegram.org/api/invites)

## License

MIT, see the LICENSE file. The text of this guide is free to copy.
