# JSON 编辑器

MyPaste extension `com.mypaste.json` (version `3.5.1`).

在页面内用 Prettier 排版 JSON：两侧都是可编辑、带行号与语法高亮的代码面板，右侧实时预览左侧，任何一侧都在出错的位置标出错误，说明写在面板下方。美化、压缩、折叠、XML、TypeScript 与复制齐全；折叠把嵌套结构收成一行、可再展开，「保留转义」开关决定结果里 \uXXXX 与 \/ 是否还原；粘贴 URL 参数、XML 或 YAML 转换后写在右侧。Prettier 内置于页面，不需要 Node，不联网，复制由宿主执行。

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

## License

MIT. See [LICENSE](LICENSE).
