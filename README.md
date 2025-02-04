<img src="https://ik.imagekit.io/unburn/greetify.svg"/>

<p align="center">Futuristic welcome card canvas library</p>

<p align="center">
    <a href="https://github.com/unburn/greetify"><b>Github</b></a> •
    <a href="https://discord.gg/66uGX7t4ww"><b>Support</b></a>
</p>

<div align="center">

[![NPM Version](https://img.shields.io/npm/v/greetify?style=flat-square&color=%2300D684)](https://www.npmjs.com/package/greetify)
[![NPM Downloads](https://img.shields.io/npm/dw/greetify?style=flat-square&color=%2300D684)](https://www.npmjs.com/package/greetify)
[![NPM License](https://img.shields.io/npm/l/greetify?style=flat-square&color=%2300D684)](https://github.com/unburn/greetify/blob/main/LICENCE)
[![GitHub Repo stars](https://img.shields.io/github/stars/unburn/greetify?style=flat-square&color=%2300D684)](https://github.com/unburn/greetify)

</div>

<div align="center">
<a href="https://github.com/sponsors/flameface"><img src="https://ik.imagekit.io/unburn/support-greetify.svg?updatedAt=1710761418683"/></a>
</div>

# Installation
```
npm install greetify
```

# Usage

## Using File System (FS)
```javascript
import { Panorama } from "greetify";
import fs from "fs";

// OR

const { Panorama } = require("greetify");
const fs = require('fs')

Panorama({
    avatar: "https://cdn.discordapp.com/avatars/786504767358238720/f65e8322c0c290e7fc1d9ad20322256b.webp",
    name: "FLAMEFACE",
    type: "WELCOME",
}).then(x => {
    fs.writeFileSync("greetify.png", x)
})
```

## In Discord Bot
```javascript
// Assuming you defined client
const { Minimal } = require("greetify");

client.on("guildMemberAdd", async member => {
    const message = `YOU ARE ${member.guild.memberCount}TH MEMBER`

    const card = await Minimal({
        name: member.user.username,
        avatar: member.user.displayAvatarURL({
            size: 4096 // For High Res Avatar
        }),
        type: "WELCOME",
        message: message
    })

    const channel = member.guild.channels.cache.get("1201155869610627212");

    return channel.send({
        files: [{
            attachment: card
        }]
    })
})
```

# Themes
## Minimal
![minimal](https://ik.imagekit.io/unburn/minimal.svg)

```javascript
const { Minimal } = require("greetify");
const fs = require('fs')

Minimal({
    avatar: "https://cdn.discordapp.com/avatars/786504767358238720/f65e8322c0c290e7fc1d9ad20322256b.webp",
    name: "FLAMEFACE",
    type: "WELCOME"
}).then(x => {
    fs.writeFileSync("greetify.png", x)
})
```

### Minimal Options
| Parameters      | Types   | Default                                            |
| --------------- | ------- | -------------------------------------------------- |
| avatar*         | string  | none                                               |
| backgroundImage | string  | https://ik.imagekit.io/unburn/greetify-default.png |
| circleBorder    | boolean | false                                              |
| message*        | string  | none                                               |
| messageColor    | string  | #FFFFFF                                            |
| name*           | string  | none                                               |
| nameColor       | string  | #00FF9E                                            |
| type            | string  | WELCOME                                            |
| typeColor       | string  | #FFFFFF                                            |


## Panorama
![panorama](https://ik.imagekit.io/unburn/panorama.svg)

```javascript
const { Panorama } = require("greetify");
const fs = require('fs')

Panorama({
    avatar: "https://cdn.discordapp.com/avatars/786504767358238720/f65e8322c0c290e7fc1d9ad20322256b.webp",
    name: "FLAMEFACE",
    type: "WELCOME"
}).then(x => {
    fs.writeFileSync("greetify.png", x)
})
```

### Panorama Options
| Parameters      | Types   | Default                                            |
| --------------- | ------- | -------------------------------------------------- |
| avatar*         | string  | none                                               |
| backgroundImage | string  | https://ik.imagekit.io/unburn/greetify-default.png |
| circleBorder    | boolean | false                                              |
| name*           | string  | none                                               |
| nameColor       | string  | #00FF9E                                            |
| type            | string  | WELCOME                                            |
| typeColor       | string  | #FFFFFF                                            |

# Licence
[GPL](https://github.com/unburn/greetify/blob/main/LICENCE)