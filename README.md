# JSON 编辑器

MyPaste extension `com.mypaste.json` (version `3.7.0`).

只在正文是 JSON 对象或数组时出现的 JSON 编辑器：在页面内用 Prettier 排版 JSON，两侧都是可编辑、带行号与语法高亮的代码面板，右侧实时预览左侧，任何一侧都在出错的位置标出错误，说明写在面板下方。美化、压缩、折叠、XML、TypeScript 与复制齐全；折叠把嵌套结构收成一行、可再展开，「保留转义」开关决定结果里 `\uXXXX` 与 `\/` 是否还原；粘贴 URL 参数、XML 或 YAML 转换后写在右侧。Prettier 内置于页面，不需要 Node，不联网，复制由宿主执行。

The manifest's `surface.match` is also an eligibility gate (`minScore: 2`): the editor is offered only for a body that starts with `{` or `[`, so plain prose, CSV and other text clips no longer see it in the picker or as the double-click default.

This repository is an independent copy extracted from the former `mypaste-code-extensions` monorepo at commit `2af6675ab1473c9e38146ea0b6da68256a293440`. It contains only this extension's tracked source files. The published `.mypaste-plugin` archives and marketplace index live in [`mypaste-extensions-catalog`](https://github.com/mypaste/mypaste-extensions-catalog).

The manifest speaks MyPaste plugin protocol v3. Installation, capability mediation, and content-digest verification are performed by the MyPaste desktop host.

## Files

- `mypaste.plugin.json`: package identity and capability declaration.
- `run.sh`, `src/`, `panel.html`, or `run`: package implementation.

## Build

```bash
bun install
bun run build
```

The generated `preview.html` is intentionally ignored; edit `src/preview.html` and `src/main.ts` instead.

## Third-party

The page bundles [Prettier](https://github.com/prettier/prettier) 3.6.2 (MIT,
Copyright © James Long and contributors) — its standalone build with the babel
and estree plugins — for JSON formatting. The license text sits in the head of
`src/preview.html`, because the generated page is the whole archive.

## License

MIT. See [LICENSE](LICENSE).
