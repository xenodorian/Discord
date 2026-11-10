# Discord Bot Setup Notes

Status: the Discord bot is not connected to Claude Code cloud sessions yet.

## What we found

1. **The Discord item in Settings is a plugin, not a connector.** Under "Yours" it shows as "Plugin". Cloud Code sessions load only connectors, so the Discord plugin does not attach to new sessions. The Connectors list in a new session showed only Google Docs, Google Drive, and Hugging Face.
2. **The Discord plugin server failed at session start** with `CONNECTION_CLOSED`. The token was not yet saved at that point. The server reads the token once, at startup.
3. **The token was saved to a file in the container** (`~/.claude/channels/discord/.env`). Container files may not carry over to a new session.
4. **An environment variable was added** (`DISCORD_BOT_TOKEN`) under Default environment, then Edit, then Environment variables. The docs say new sessions pick it up. Not yet verified. The Discord plugin was written to read its `.env` file, so it may ignore the variable.

## Next steps

1. Check that the Discord variable appears in a new session (`env | grep DISCORD_BOT_TOKEN`).
2. If the server still fails, run the bot on a computer instead. Cloud sessions can't run this plugin reliably.
3. Reset the bot token in the Discord Developer Portal (Bot, then Reset Token). The original token was pasted into a chat, so treat it as exposed.

## Commands

- Save the token locally: `/discord:configure <token>`
- Check status: `/discord:configure`
- Pair a user: `/discord:access pair <code>`
- Lock access: `/discord:access policy allowlist`

## Security

- Never paste the token into chat or commit it to the repo.
- Keep `~/.claude/channels/discord/.env` private (permissions 600).
- Anyone who can use this environment can see environment variables.
