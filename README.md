<p align="center">
  <img src="https://e.top4top.io/p_38721hu6c1.jpg" width="250"/>
</p>

<h1 align="center">WhatsApp Baileys</h1>

<p align="center">
  Open-source library for building fast, stable WhatsApp automation and integrations over WebSocket — no browser required.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/node-%3E%3D20-brightgreen" />
  <img src="https://img.shields.io/badge/license-MIT-blue" />
  <img src="https://img.shields.io/badge/multi--device-supported-success" />
</p>

> [!NOTE]
> `"@whiskeysockets/baileys": "github:xvnsync/xbails"` is an unofficial WhatsApp Web API library. Not affiliated, not authorized, not maintained, not sponsored, and not endorsed by WhatsApp or Meta.
>
> Use Baileys responsibly, and comply with the WhatsApp Terms of Service and applicable laws.

---

# Table of Contents 

- [Requirements](#requirements)
- [Installation](#installation)
- [Import](#import)
- [Import AI Rich Message Builder](#import-ai-rich-message-builder)
- [Quick Start](#quick-start)
  - [With QR Code](#with-qr-code)
  - [With Pairing Code](#with-pairing-code)
- [Sending Message](#sending-messate)
  - [Generic Send / Relay](#generic-send--relay)
  - [Simple Senders](#simple-senders)
  - [Sending Message with Participant](#sending-message-with-participant)
- [Why Choose WhatsApp Baileys?](#why-choose-whatsapp-baileys)
- [Contributors](#contributors)
- [Contact Developer](#contact-developer)

---

# Requirements

- Node.js **>= 20**
- Optional peer dependencies depending on the features you use:
  - `sharp` or `jimp` for image processing
  - `link-preview-js` for link previews
  - `audio-decode` for audio waveform handling
  
---

## Installation

```bash
npm install @whiskeysockets/baileys
```

Add it to your `package.json`:

```json
{
  "dependencies": {
    "@whiskeysockets/baileys": "github:xvnsync/xbails"
  }
}
```

---

## Import

```javascript
const {
  default: makeWASocket,
  // Other Options
} = require('@whiskeysockets/baileys');
```

---

## Import AI Rich Message Builder

```javascript
const {
  default: makeWASocket,
  useMultiFileAuthState,
  DisconnectReason,
  Button,
  ButtonV2,
  Carousel,
  AIRich,
  Toolkit,
  MessageBuilder,
  MB
} = require('@whiskeysockets/baileys');
```

> [!NOTE]
> MessageBuilder sudah terintegrasi. Kamu tidak perlu memasang `baileys-mbuilder` secara terpisah.

---

## Quick Start

### With QR Code

```javascript
const {
  default: makeWASocket,
  Browsers
  // Other Options
} = require('@whiskeysockets/baileys');

const client = makeWASocket({
  browser: Browsers.ubuntu('Chrome'),
  printQRInTerminal: true
});
```

### With Pairing Code

```javascript
const {
  default: makeWASocket,
  fetchLatestWAWebVersion,
  Browsers
} = require('@whiskeysockets/baileys');

const client = makeWASocket({
  browser: Browsers.ubuntu('Chrome'),
  printQRInTerminal: false,
  version: fetchLatestWAWebVersion(),
  auth: state
});

const number = "628XXXXX";
const code = await client.requestPairingCode(number.trim()); // Use (number, "XXXXXXXX") for custom pairing

console.log("Ur pairing code : " + code);
```

---

## Sending Message

### Generic Send / Relay

```javascript
// relayMessage — sends a raw message object, bypassing the sendMessage pipeline
await client.relayMessage(m.chat, {
  conversation: 'XvnSynC'
})

// sendMessage — the standard way to send a message
await client.sendMessage(m.chat, {
  text: 'XvnSynC'
})
```

### Simple Senders

```javascript
await client.sendText(jid, 'Hi!', { contextInfo: { mentionedJid: [jid] } })
await client.sendImage(jid, { url: './photo.jpg' }, 'image caption')
await client.sendVideo(jid, { url: './clip.mp4' }, 'video caption')
await client.sendAudio(jid, { url: './clip.mp3' })
await client.sendLocation(jid, 'Location name', -6.2, 106.8, 'https://maps.example', '1234567890')
await client.sendPoll(jid, 'Pick one', ['Option 1', 'Option 2', 'Option 3'], /* multiSelect */ true)
await client.sendQuiz(jid, 'Correct answer?', ['1', '2', '3'], /* correctIndex */ '2')
```

### Sending Message with Participant

```javascript
await client.sendMessage(m.chat, {
  text: "XvnSynC"
}, {
  ptcp: true
});
```

---

## Why Choose WhatsApp Baileys?

Because this library offers high stability, full features, and an actively improved pairing process. It is ideal for developers aiming to create professional and secure WhatsApp automation solutions. Support for the latest WhatsApp features ensures compatibility with platform updates.

---

## Contributors

<table>
  <tr>
    <td align="center">
      <a href="https://github.com/xvnsync">
        <img src="https://github.com/xvnsync.png" width="80px;" style="border-radius:50%;" alt="Main contributor"/>
        <br /><sub><b>Melvin</b></sub>
      </a>
    </td>
  </tr>
</table>

---

## Contact Developer

For questions, support, or collaboration, feel free to contact the developer:

- **Telegram**: [Telegram Contact](https://t.me/luyatiem)
- **Channel WhatsApp**: [Channel WhatsApp](https://whatsapp.com/channel/0029VbDlfld4yltRwFKFL73X)
- **Channel Telegram**: [Channel Telegram](https://t.me/aboutvin7x)
