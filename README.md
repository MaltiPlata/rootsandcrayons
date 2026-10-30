# Roots & Crayons website

The whole site is one file, `index.html`. Everything you'd want to change lives in two blocks near the bottom of it: **CONFIG** (links, Kit, photos) and **DATA** (packs, prices, alphabet, holidays). Search the file for `CONFIG` to jump there.

The Shop Launch Kit page (in your Claude artifacts) has the emails, store copy and buy links mentioned below, ready to copy.

## Before it goes live

1. **Kit form.** In Kit, open your form, then Embed > HTML. Copy the address inside `action="..."` (it looks like `https://app.kit.com/forms/1234567/subscriptions`) into `KIT_FORM`.
2. **Kit fields.** In the same form, use the + button to add two fields saved as custom fields: **Dialect** and **Birthday month**. The page fills them in.
3. **Free pack and welcome gift.** In the form's settings, turn on the confirmation email, paste in the email from the Shop Launch Kit, and set its button to redirect to `https://rootsandcrayons.com/thank-you.html`. That page has the four Feelings PDFs and the welcome coloring sheet (they all live in `free/`). There's no discount code: the welcome gift is the coloring sheet.
4. **Buy links.** Each time a product goes live in Kit or Etsy, paste its link into the Shop Launch Kit. It builds the `BUY_LINKS` block for you: copy it over the one in `CONFIG`, or ask Claude to put it in. A pack with no link sends people to your Etsy shop (`LINKS.etsy`), and shows "Coming soon" if that's empty too. Holiday packs show "Coming in November" and so on until their link is in.
5. **Photos.** Drop them into `photos/` using the names in `photos/README.txt`. Add `?photos` to the address to see where each one goes.
6. **Test.** Sign up with your own email on your phone, tap the button in the email and make sure the downloads open.

## Changing things later

- **Packs, prices, bundles and holiday packs** come from the pack builder, so the site always matches the shop. After adding a pack or changing a price there, Claude runs `site_data.py`, which rewrites the block between `PRODUCTS (from the pack builder...)` and `end of PRODUCTS`, and adds any new product to `BUY_LINKS` without touching the links already there. Please don't edit that block by hand: the next run replaces it.
- **The shelves.** Packs sit on shelves by collection (Letters & Reading, All About Me, Big Imaginations and so on), each opening with its bundle. The buttons above them show one shelf at a time.
- **The message bar at the top:** `SEASONS` picks a message by date. Add next year's dates each fall.
- **Birthday printables:** `BIRTHDAY`. The Birthday Party pack takes its price and link from the shop data.
- **Alphabet:** one row per letter in `ALPHABET`. To add recordings, put `01.mp3` to `39.mp3` in a folder and set `ALPHABET_AUDIO`.

## Files

- `index.html` is the page.
- `thank-you.html` is where the welcome email sends new subscribers: the Feelings pack and the welcome coloring sheet. Search engines are told not to list it.
- `free/` holds the free downloads: the Feelings pack (color and ink-saver, US Letter and A4), the welcome coloring sheet, and the free coloring sheet for each holiday drop's email.
- `social/` holds the pictures for the year of Instagram and Facebook posts. The post files and Metricool link to them here, so leave the names as they are.
- `pins/` holds the Pinterest pins. The bulk-upload file links to them here.
- `og-image.png` is the picture Facebook, Instagram, Pinterest and texts show when someone shares the link.
- `photos/` holds your photos.
