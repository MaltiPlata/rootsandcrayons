# Roots & Crayons website

The whole site is one file, `index.html`. Everything you'd want to change lives in two blocks near the bottom of it: **CONFIG** (links, Kit, photos) and **DATA** (packs, prices, alphabet, holidays). Search the file for `CONFIG` to jump there.

The Shop Launch Kit page (in your Claude artifacts) has the emails, store copy and buy links mentioned below, ready to copy.

## Before it goes live

1. **Kit form.** In Kit, open your form, then Embed > HTML. Copy the address inside `action="..."` (it looks like `https://app.kit.com/forms/1234567/subscriptions`) into `KIT_FORM`.
2. **Kit fields.** In the same form, use the + button to add two fields saved as custom fields: **Dialect** and **Birthday month**. The page fills them in.
3. **Free pack.** In the form's settings, turn on the confirmation email, paste in the email from the Shop Launch Kit, and set its button to redirect to `https://rootsandcrayons.com/thank-you.html`. That page has the four Feelings PDFs (they live in `free/`) and the welcome code.
4. **Welcome code.** Create BAREV20 for 20% off in Kit and on Etsy. If you pick a different code, change `WELCOME_CODE` near the bottom of `thank-you.html` and the line in the email to match.
5. **Buy links.** Each time a product goes live in Kit, paste its link into the Shop Launch Kit. It builds the `BUY_LINKS` block for you: copy it over the one in `CONFIG`, or ask Claude to put it in. Etsy listing links work too. A pack with no link sends people to your Etsy shop (`LINKS.etsy`), and shows "Coming soon" if that's empty too.
6. **Photos.** Drop them into `photos/` using the names in `photos/README.txt`. Add `?photos` to the address to see where each one goes.
7. **Test.** Sign up with your own email on your phone, tap the button in the email and make sure the downloads open. Buying one pack yourself with the code is the best way to see exactly what customers get.

## Changing things later

- **Prices:** `price` on each pack in `PACKS`, the bundles in `BUNDLES`, and `CLASSROOM_PRICE`. The totals and "save" amounts in the copy update on their own.
- **Holiday packs:** when one is listed, change its `status` and add its `url` in `HOLIDAYS`.
- **The message bar at the top:** `SEASONS` picks a message by date. Add next year's dates each fall.
- **Alphabet:** one row per letter in `ALPHABET`. To add recordings, put `01.mp3` to `39.mp3` in a folder and set `ALPHABET_AUDIO`.

## Files

- `index.html` is the page.
- `thank-you.html` is where the welcome email sends new subscribers. Search engines are told not to list it.
- `free/` holds the free Feelings pack: color and ink-saver, US Letter and A4.
- `og-image.png` is the picture Facebook, Instagram, Pinterest and texts show when someone shares the link.
- `photos/` holds your photos.
