# Working rules

## Delegate low-level work to Haiku bots
- Any task that does not need higher reasoning or deep thought (bulk reading, extraction, comparison against a source, formatting, fetching, simple file edits) goes to a subagent run with `model: haiku`, to save usage.
- When there is a lot of low-level work, split it and dispatch several Haiku bots in parallel so it finishes quickly.
- Keep judgment-heavy work (planning, final writing, resolving conflicts between sources, reviewing bot output) for the main model, and spot-check bot results before relying on them.

## Note formatting (Catan and other notes)
- Do not use bullet points in notes. Write plain paragraphs.
- In the Catan outline's Notes tab, start each new day's (session's) notes with a page break.
- Put an empty paragraph above and below every header, for breathing room.
- Indent note paragraphs to match the outline's Merchants tab: first-line indent 36 pt and left indent 36 pt. Headers and the date/party lines stay flush left.

## Reading the DM's posts (Barovia, Catan, all campaigns)
- Each Discord user plays one character per campaign (Barovia: sideshow031 = Dax, potoooooooo = Bohdana, fleshvalleyart_maro = Zenobia, scruffy8774 = Circuit, then Zin from July 2024, and both from mid-April 2025).
- A DM post that @tags one player and says "you" means that player's character.
- "You" with no tag, or with an @everyone/role ping, means the whole party.
- Never guess who "you" is from context alone; check the raw archive (pbp_full.jsonl keeps the <@id> tags) before attributing an action.
