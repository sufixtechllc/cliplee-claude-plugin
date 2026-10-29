---
name: cliplee-video
description: Make an AI video with Cliplee. Use when the person asks to create, price or check a Cliplee video, or asks about their Cliplee credits or videos.
---

# Making a video with Cliplee

Cliplee turns a text description into a video and charges credits from the person's own
Cliplee account. The `cliplee` connector signs them in with OAuth the first time.

1. **Understand the video.** Ask for anything missing: what happens, the style, the length
   (5–15 seconds, or 20, 30, 45 or 60 seconds made from joined clips) and the shape
   (vertical 9:16, landscape 16:9 or square 1:1). Use `list_video_models` if they ask about
   models or quality.
2. **Price it first.** Call `quote_video` with the length and settings. Tell the person the
   model, length, shape and the credits it will use (and the credits held while it runs).
   If `canCreate` is false, explain the `problems` instead of trying to create it.
3. **Create only after a clear yes.** Call `create_video` with a detailed `prompt` and
   `expectedCredits` set to the quoted credits. If the price changed, quote again and ask again.
   Never create a video the person has not agreed to.
4. **Follow it.** Videos take a few minutes. Use `get_video` to report progress, and give the
   `link`: the finished video is watched and downloaded in Cliplee (signed in).

Other tools: `get_account` (plan and credits), `list_videos`, `search` and `fetch` (their videos).

The connector makes text-to-videos only. Avatar videos, image-to-video and voice cloning are
made in the Cliplee studio at https://cliplee.com.
