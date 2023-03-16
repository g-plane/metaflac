# 🎶 @gplane/metaflac

Library for processing metadata of [FLAC (Free Lossless Audio Codec)](https://xiph.org/flac/) files, which can be run on Deno, browsers and Node.js.

> Working in progress.

## 🫕 Usage

```ts
import * as fs from 'node:fs/promises'
import { parse, createTagView, dump } from '@gplane/metaflac'

const file = await fs.readFile('./input.flac')
const metadata = parse(file)

const tagView = createTagView(metadata)
// reading tag data
console.log(tagView.artist)
// writing tag data
tagView.title = 'xyz'
// removing
tagView.genre = null

const modifiedFile = dump(metadata, file)
await fs.writeFile('./output.flac', modifiedFile)
```

## 📃 License

MIT License

Copyright (c) 2021-present Pig Fang
