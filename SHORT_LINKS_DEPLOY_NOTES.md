# EPOCH short tracked links

Adds four Netlify 301 redirects:

- `/tiktok` -> TikTok organic bio UTM
- `/instagram` -> Instagram organic bio UTM
- `/facebook` -> Facebook organic first-comment UTM
- `/youtube` -> YouTube organic bio UTM

## Deploy

Upload both files to the root of `morhason-afk/Epoch_LP` on branch `main` and commit. `_redirects` must have exactly that name, with no extension. Netlify will publish automatically.

The full destination URLs remain in the browser after redirect, so UTM attribution is preserved while the shared link stays short.
