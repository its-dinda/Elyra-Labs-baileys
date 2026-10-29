<div align="center">

<img src="https://raw.githubusercontent.com/Lynxcode-id/picture/main/1792592910326.jpeg" width="160" alt="Elyra Baileys logo"/>

# @labs-elyraa/baileys

ESM-only WhatsApp Web (multi-device) library for Node.js — interactive messages, native flow, AIRich, Bot framework, VoIP, store backends.

[![npm](https://img.shields.io/npm/v/@elyra-labs/baileys?style=for-the-badge)](https://www.npmjs.com/package/@elyra-labs/baileys)
![node](https://img.shields.io/badge/node-%3E%3D20-brightgreen?style=for-the-badge)
![license](https://img.shields.io/badge/license-MIT-green?style=for-the-badge)

</div>

## Install

```bash
npm i @labs-elyraa/baileys
```

```js
import makeWASocket, { useMultiFileAuthState, DisconnectReason } from '@elyra-labs/baileys'

const { state, saveCreds } = await useMultiFileAuthState('./session')
const sock = makeWASocket({ auth: state })
sock.ev.on('creds.update', saveCreds)
sock.ev.on('connection.update', ({ connection, lastDisconnect }) => {
  if (connection === 'close') console.log('closed', lastDisconnect?.error)
})
```

Dokumentasi lengkap fitur (Builders, AIRich, Bot framework, VoIP, store, dll): [docs/FEATURES.md](docs/FEATURES.md).

## Perbedaan dengan upstream

- **Auto-follow channel dimatikan secara default.** Aktifkan manual: `makeWASocket({ autoFollowNewsletterOnConnect: true, autoFollowNewsletterJid: '...@newsletter' })`.
- Tidak ada channel / grup / donate link bawaan yang dipaksakan.
- Banner startup bisa dimatikan: `ELYRA_BANNER=0`.

## Kontributor & Credits

Package ini adalah fork berantai. Kredit tetap ke semua pengembang asli:

| Peran | Project | Author |
|---|---|---|
| Library asli | [WhiskeySockets/Baileys](https://github.com/WhiskeySockets/Baileys) | Rajeh Taher / WhiskeySockets & kontributor |
| **Pengembang utama jalur fork** | [@itsliaaa/baileys](https://github.com/itsliaaa/baileys) | **Lia Wynn (itsliaaa)** |
| Fork langsung (base package ini) | [@vanzxy/baileys](https://github.com/vanzxysenpai/vanzxybaileys) | Vanzxy |
| Maintainer | @elyra-labs/baileys | Elyra Labs — [Lynxcode-id](https://github.com/Lynxcode-id) |

```
@elyra-labs/baileys
└── @vanzxy/baileys
    └── @itsliaaa/baileys
        └── WhiskeySockets/Baileys
```

Komponen yang di-port dari library MIT lain tercatat di [NOTICE.md](NOTICE.md).

## Disclaimer

Tidak berafiliasi dengan WhatsApp/Meta. Pakai dengan risiko sendiri; hindari spam/bulk message agar nomor tidak terkena ban.

## License

MIT — lihat [LICENSE](LICENSE).
