# Shiki TipTap Extension

Use [Shiki](https://shiki.style/) syntax highlighting for codeblocks in [TipTap](https://tiptap.dev/).

## Installation

```console
npm install shiki tiptap-extension-code-block-shiki
```

## Usage

The extension extends [CodeBlock](https://tiptap.dev/docs/editor/api/nodes/code-block).

```ts
import { Editor } from '@tiptap/core'
import StarterKit from '@tiptap/starter-kit'
import CodeBlockShiki from 'tiptap-extension-code-block-shiki'

new Editor({
  extensions: [
    StarterKit.configure({ codeBlock: false }),
    CodeBlockShiki.configure({
      defaultTheme: 'tokyo-night'
    }),
  ],
})
```

Go into your TipTap editor, write `` ```ts ``, press <kbd>Enter</kbd>, and write some code! It loads the language on the fly.

## Settings

The extension extends [CodeBlock](https://tiptap.dev/docs/editor/api/nodes/code-block) and forwards its settings. It additionally adds the following settings:

### `defaultTheme`

Which theme to use by default. See https://shiki.style/themes.

### `defaultLanguage`

Which language to use, when no language was provided. See https://shiki.style/languages.

## Notes

### Lazy loading

The library loads themes and languages asynchronously.

### Unknown language fallback

When you use a language which isn't supported by Shiki, it silently falls back to no syntax highlighting.

## Credits

Most of this library is just combining code from two other libraries:

- [`@tiptap/extension-code-block-lowlight`](https://github.com/ueberdosis/tiptap/tree/main/packages/extension-code-block-lowlight) by [TipTap](https://tiptap.dev)
- [`prosemirror-highlight`](https://github.com/ocavue/prosemirror-highlight) by [ocavue](https://github.com/ocavue)