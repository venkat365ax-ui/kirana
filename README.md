# Kirana Store – grocery ordering app

A simple phone app for ordering groceries from a kirana shop. Customers add items to the cart and fill in their details. When they place the order, WhatsApp opens with the full order typed out, sent to the shop's number.

## Files
| File | What it is |
|---|---|
| index.html | The whole app. Shop details and products are at the top. |
| manifest.json | Name, colour and icon used when the app is installed |
| sw.js | Makes the app open fast and work offline |
| icon-192.png, icon-512.png, icon-maskable-512.png | App icons |

## Step 1 – Put in your shop details
Open `index.html` in any text editor (Notepad works). Near the top, find `CONFIG` and change:
- `shopName`: for example `"Sri Lakshmi Kirana Store"`
- `whatsappNumber`: the shop's WhatsApp number with 91 in front and no spaces, e.g. `"919876543210"`
- `upiId`: the shop's UPI ID, if customers should be able to pay by UPI. Otherwise leave it `""`.
- `deliveryFee`, `minOrder`: amounts in ₹ (0 = free / no minimum)

Under it, `PRODUCTS` lists every item. Each line has a name, size and price. Copy a line to add an item and delete a line to remove one. The prices included are only samples.
Set `popular: true` on an item to show it on the home screen.

## Step 2 – Put it online (free)
**Option A – GitHub Pages**
1. Create a free account at github.com.
2. Create a new **public** repository, e.g. `kirana`.
3. Choose **Add file → Upload files** and drop in all the files from this folder. Then press **Commit**.
4. Go to **Settings → Pages**, set Source to **Deploy from a branch** with branch **main** and folder **/ (root)**, then press **Save**.
5. After 1–2 minutes your link is ready: `https://<your-username>.github.io/kirana/`

**Option B – Netlify**
1. Create a free account at netlify.com.
2. Go to **Sites → Add new site → Deploy manually** and drag this whole folder in.
3. You get a link like `https://something.netlify.app`. You can rename it in Site settings.

## Step 3 – Install on the phone
- **Android (Chrome):** open the link, tap **⋮ → Add to Home screen / Install app**.
- **iPhone (Safari):** open the link, tap **Share → Add to Home Screen**.

The app now has its own icon and opens full-screen. Share the same link with customers so they can install it too.

## Updating prices later
Edit `index.html`, upload it again (to GitHub or Netlify), and change `kirana-v1` to `kirana-v2` in `sw.js` so phones pick up the new version.
