# JavaScript for Deck

`typescript-language-server`, for `.js` and `.jsx`.

The same server the TypeScript definition names — one server backs both languages, which is what
`serverId` expresses: Deck starts one session per `(serverId, project root)` rather than one per
language.

A project is anything with a `package.json`.

```sh
npm i -g typescript-language-server typescript
```

Both are needed: the server is a wrapper, and `typescript` is the compiler it drives.

## Installing it

From inside Deck: **Settings -> Plugins -> Browse**, pick it, and it loads straight away.

By hand: copy this folder into `%APPDATA%\Deck\languages\` (`Deck-Dev` for a debug build).
`docs/languages.md` in the Deck repository documents the format.

## What a definition can and cannot do

It is **data**, not code. `language.json` is parsed field by field and never executed, which is
why a language is a different kind of thing from a plugin even though both are folders Deck
reads at startup. The worst a malformed one can do is skip itself.
