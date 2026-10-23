# Assessment notes

## What changed
- Rebuilt the single-file storefront with responsive layout, two brand-approved font families, accessible controls, focus states, reduced-motion support, and the required page sections.
- On phones, moved search into a full-width row below the logo and cart instead of leaving it compressed beside the cart.
- Replaced legacy external CSS/JS libraries with native HTML, CSS, and JavaScript. Reworked search/filter/sort composition, wishlist, product details, cart quantities, delivery check, and newsletter form behavior.
- Cart state now stores only product IDs and quantities. Prices are always read from `PRODUCTS`; quantities are constrained to five and stock. `WELCOME10` is case-insensitive, applies once to eligible non-gift items, requires a ₹399 subtotal and caps at ₹150. Shipping is ₹49 below ₹599 after discount and free at/above ₹599. Only the final total is rounded.
- Added title/description, canonical and social metadata, Organization/Product/FAQPage JSON-LD, and the approved FAQ answers.
- Kept the `API` object unchanged, retained the checkout form action/method/field names, and preserved footer legal wording.

## What the AI got wrong / risks caught
- An earlier assessment note incorrectly claimed the supplied cart failed on empty local storage and read prices from displayed text. Review of `loadCart()` and `subtotal()` confirmed the code already handled those cases, so those claims have been removed.
- A pending pincode lookup could show its result after the shopper edited the field, pairing an old delivery estimate with a new pincode. Browser testing reproduced it; input changes now invalidate the pending result and clear its status.
- If all eligible tea was removed after applying WELCOME10, checkout still sent the code despite showing no discount. Checkout now revalidates the discount and sends an empty coupon for an ineligible cart.
- The supplied hero artwork contains the misspelling "Mistawale" and unsupported health/quality claims. I cropped those out and used the cup-and-hills portion instead.
- The original gift-box image included unverified copy and mislabeled Darjeeling First Flush as green tea, while `PRODUCTS` lists it as Black. The supplied replacement artwork is retained, resized and optimized as a JPEG under 100 KB.
- The README requires a free-shipping threshold but does not state its amount. I retained the existing ₹599 value temporarily; please confirm.

## Images
- Used six supplied product images to create square 640px JPEG crops at quality 82 for products 101–106; each optimized file is under 100 KB. The original multi-megabyte PNGs were removed after verifying the crops, to keep the submission below the 20 MB limit.
- Product 108 uses the supplied gift-box artwork, resized to 640px and optimized as a JPEG under 100 KB. The optimized JPEG is the project asset; no source PNG is included in `images/`.
- Cropped the supplied hero banner to the tea cup and hills, then saved it as `images/hero-moment.jpg` at 97 KB. Updated the page hero and social preview image metadata to use this file.
- The supplied source images' generation tool/source was not identified in the workspace.
- The supplied Hibiscus Rose artwork is resized to 640px and optimized as a JPEG under 100 KB. The optimized JPEG is the project asset; the logo remains SVG.
- A countdown is not shown because no real promotion or end date is specified; inventing urgency would be misleading.
- Removed duplicate optimized-name PNG copies and the unreferenced legacy placeholders `p107.svg` and `p108.svg`. The current `images/` folder contains the referenced optimized assets, not the source PNGs.

## How I tested it
- Chromium integrated browser opened the file directly. Checked 360px and desktop widths; neither had horizontal overflow.
- Tested combined Black filter + `assam` search, sold-out-last ordering, add to cart, quantity increase, and product-derived totals: ₹349 + ₹49 shipping, then ₹698 with free shipping.
- Tested coupon at the ₹399 minimum (₹408 total after discount, shipping and final rounding), the ₹150 cap, quantity maximum of five, and rejection for a gift-only cart.
- Verified checkout sends an empty coupon after removing all eligible tea, and still sends WELCOME10 when eligible tea remains in the cart.
- Tested pincode validation (`12`), serviceable delivery (`734001`, 2 days), not-serviceable result (`123456`), editing the pincode during an in-flight check, and checkout fields (`items` JSON plus `WELCOME10`).
- Confirmed all eight product card images load in the browser; all product cards use optimized JPEGs.
- Rechecked that every image referenced by the page exists after asset cleanup; no broken image references or browser JavaScript errors were found.
- After the mobile-header change, rechecked at 360px: no horizontal overflow, all 11 page images loaded, and no JavaScript page errors. Rechecked combined category/search, coupon and quantity limits, plus valid, invalid and unserviceable pincode responses.
- Packaged the submission as `mistvale-assessment.zip` with `index.html`, `images/`, `NOTES.md`, and `PROMPTS.md`; verified the ZIP contents and size.
- Keyboard-only, screen-reader, Lighthouse and other browser testing remain outstanding.

## Questions for the team
- Please confirm whether free shipping starts at ₹499 or ₹599; the page previously showed both values.
- Please confirm the intended newsletter destination/integration. The current signup explicitly identifies itself as a demo and does not claim to subscribe anyone.
- Should the final copyright year/brand spelling be updated? I left the approved legal paragraph unchanged as required.

## Time spent
Approximately 40 minutes of active implementation, review, and local browser checks.

## Extra features
- Wishlist saved locally in the browser.
- Product quick view and combined search/filter/sort.

## With more time I would
- Generate and optimize realistic, consistent tea pack photography, confirm the shipping threshold, and complete responsive, keyboard, accessibility, coupon and checkout-contract tests.
