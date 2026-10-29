# Cliplee for Claude

Make AI videos with [Cliplee](https://cliplee.com) from Claude.

- See your plan and credits.
- Price a text-to-video before anything is made.
- Create it once you confirm, using your own Cliplee credits at the same prices as the Cliplee studio.
- Follow its progress and get the link to watch and download it in Cliplee.

## What's inside

- `.mcp.json` connects Claude to the Cliplee MCP server at `https://cliplee.com/mcp`
  (Streamable HTTP). It uses OAuth 2.1 with dynamic client registration and PKCE: you sign in
  to Cliplee and choose Allow. No API keys or passwords are stored in this plugin.
- `skills/cliplee-video` guides Claude to quote a video and get your agreement before it
  spends credits.

## Tools

| Tool | What it does | Changes anything |
| --- | --- | --- |
| `get_account` | Plan, credits and Free-plan limits | No |
| `list_video_models` | Models, lengths, shapes, resolutions and credits per second | No |
| `quote_video` | Credits a video will use, and whether it can be made now | No |
| `create_video` | Starts a text-to-video at the confirmed credits | Yes (spends credits) |
| `list_videos` | Your recent videos with status and links | No |
| `get_video` | Progress, credits and the link of one video | No |
| `search` / `fetch` | Find your videos and read one | No |

## Requirements

A Cliplee account. Create one free at https://cliplee.com/signup.

## Privacy and support

- Privacy Policy: https://cliplee.com/legal/privacy (see "Connected apps")
- Terms of Service: https://cliplee.com/legal/terms
- Support: https://cliplee.com/contact or support@cliplee.com
- Disconnect any time in Cliplee under Settings → Connected apps.
