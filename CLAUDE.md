# Laboratorio

A single-file Spanish reading lab (Latin American Spanish): everything is in `index.html`, served by GitHub Pages from `main`. It is the Spanish sibling of Sprachlabor (huss234/sprachlabor) and shares its structure, but not its storage, data repository, name, marks or colours.

## Before any visible change

Read `DESIGN.md` first and follow it exactly. It is this app's own design
language (Ulm/Swiss functionalist structure, hairline, with Talavera cobalt and
saffron on lime-wash paper). It is not Material Design, M3 Expressive, Fluent
or Apple HIG, and nothing from those belongs here.

- Use only the CSS variables and components listed in `DESIGN.md`.
- Don't invent colours, radii, shadows, fonts, easing curves or icon styles.
- Reuse an existing class or helper (`openMenu`, `askConfirm`, `toast`, `.btn`, `.panel`, `.menu`…) before writing new ones.
- If something genuinely new is needed, build it from the tokens and add it to `DESIGN.md` in the same change.
- Check light and dark themes, and 390px as well as desktop width.

## Other house rules

- The version lives in `APP_VERSION` and in the comment on line 2 of `index.html`; bump both together (1.0 → 1.1).
- Sync and storage are described in the comment block above `const GH`. Any new synced data needs a record type in `Sync.diff()`, `journalFiles()`, `writeSnapshot()` and `applyFile()`. A lesson edit must bump `updatedAt`.
- Never rename a storage key without migrating the saved data.
- Laboratorio and Sprachlabor are both served from huss234.github.io, one origin, so they share localStorage and IndexedDB. Every key here is prefixed for Laboratorio (`laboratorio-…` keys, IndexedDB `laboratorio`, `lb.spkb`, format `laboratorio.lesson`, data repo `laboratorio-data`). Never reuse a Sprachlabor key.
- Spanish, not German: lesson text lives in `es` fields; a noun's gender is `el` or `la` (its real gender; the article it is said with comes from the word itself, so `el agua` has gender `la`); respellings follow the Latin American sound (c, z = s; ll, y = y); voices prefer es-MX, es-US and es-419 over es-ES.
