# Christmas by the Fire — seanmscott.com/christmas

A full-screen page that loops the cozy backdrop (Ramsey by the fire) and plays the
Christmas Spotify playlist on the Sonos Beam, with a "now playing" card.

Files in this folder:
- `index.html` — the page
- `backdrop.mp4` — the 28-second seamless loop (~4 MB)

## 1. Create the Spotify app (one time, ~10 minutes)

1. Go to https://developer.spotify.com/dashboard and sign in with your Spotify Premium account.
2. Click **Create app**.
   - App name: `Christmas by the Fire` (anything works)
   - App description: anything
   - Redirect URI: `https://seanmscott.com/christmas/` (exactly this, including the trailing slash). Click **Add**.
   - APIs used: tick **Web API** and **Web Playback SDK**.
   - Accept the terms and **Save**.
3. Open the app's **Settings** and copy the **Client ID**. (You do NOT need the Client Secret.)
4. Under **User Management**, add your own Spotify account's name and email.
   Development-mode apps allow up to five people; add family members here if they will use it too.

## 2. Add the Client ID to the page

Open `index.html` in a text editor and replace

    const CLIENT_ID = 'PASTE_YOUR_SPOTIFY_CLIENT_ID_HERE';

with your Client ID (keep the quotes). The Client ID is safe to publish; there is no secret in this page.

## 3. Publish on seanmscott.com

Copy this `christmas` folder into the root of the `sean-sms/seanmscott.com` repository
(next to your `dailybriefs` folder), then commit and push:

    git add christmas
    git commit -m "Add Christmas by the Fire page"
    git push

After GitHub Pages rebuilds (a minute or two), open https://seanmscott.com/christmas/

## 4. Use it on the LG TV

1. Open the LG **Web Browser** app and go to `seanmscott.com/christmas`.
2. Press **Sign in with Spotify** (only needed the first time on that browser).
3. Under **Play on**, choose the **Beam**, then **Play the playlist**.
   - If the Beam isn't listed: play anything on it once from the Spotify app on your phone, then press ↻.
4. Press **Full screen**. The controls fade away after a few seconds; move the remote's pointer to bring them back.

Tip: in the Sonos app, turn off **TV Autoplay** for the Beam so it doesn't switch to the TV's sound.

If the TV browser gives trouble, open the same page on the Mac and AirPlay or HDMI it to the TV.
On a computer you can also pick **This browser** to play the music from the computer itself.

## Changing things later

- Different playlist: change `PLAYLIST_URI` in `index.html` (the ID is the part after `/playlist/` in the Spotify link).
- Different address: rename the folder, and update the Redirect URI in the Spotify dashboard to match.
- Preview the layout without signing in: add `#demo` to the address.
