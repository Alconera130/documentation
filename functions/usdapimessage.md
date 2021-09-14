---
description: Sends a Message using raw Discord API.
---

# $apiMessage

## Description

```javascript
"sends a Message using raw discord api"
```

## Status

```javascript
"BETA"
```

## Usage

```javascript
"$apiMessage[channelID;content;embed;component;referenceMessageID:mentionTheUser(true/yes/false/no);return Id(yes/no)]"
```

## Fields

### ChannelId

> ```javascript
> "Where to Send The Message"
> ```

### Content

> ```javascript
> "Sends the normal message"
> ```

### Embed

> ```javascript
> "Sends the embedded message"
> ```
>
> **Note**:
>
> This uses embed-errors in their full form.
>
> example: {author:hi} won't work but {author:hi::} will
>
> You can see them [here](https://github.com/USERSATOSHI/documentation/blob/Aoijs-V5/topics/message%20formatting/parsers.md#embedparser)
> 
> Do not forget to add {newEmbed:} for every embed, 10 embeds per message only
> 
> example: {newEmbed:{description:hi}}
>
> Color only supports hex code and int for now.
>
> ### Components
>
> You can see them [here](https://github.com/USERSATOSHI/documentation/blob/Aoijs-V5/topics/message%20formatting/parsers.md#componentparser)

### Reference

> ```javascript
> "This is for replying to the user"
> ```
>
> **Format:** messageID:mentionTheUser\(true/false\)

### ReturnID

> ```javascript
> "Returns the id of the message sent"
> ```

## Example

```javascript
bot.command({
name:"hi",
code:`
$apiMessage[$channelId;hi;{author:hi::}{title:hello}{field:ok:lol:no}{color:#8700ff}{footer:hmmm:$authorAvatar};{actionRow:click me,2,1,click};$messageID:true;no]
`
})
```