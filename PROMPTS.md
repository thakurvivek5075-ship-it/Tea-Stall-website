# Prompt log

## Prompt 1
- Tool: GitHub Copilot
- Type: code
- Prompt:
  > Analyze the provided Mistvale Tea Co. website project carefully.Read README.md and BRAND.md, and inspect the existing index.html
  > - Fix the existing bugs and functional issues
  >
  > - Improve the overall design and user experience
  >
  > - Improve the shopping experience and usability
  >
  > - Create professional product images where required
  
- Context: The complete attached README.md, BRAND.md, and index.html were also supplied with this prompt.
- Outcome: modified
- Why: The implementation preserves the provided store contracts and applies the attached brand rules. Custom SVG artwork was made locally because no image-generation tool was available; it is not represented as generated photography.

## Prompt 2
- Tool: GitHub Copilot
- Type: code
- Prompt:
  > check this code  fix bugs and errors according README.md
- Outcome: modified
- Why: Testing exposed a pincode lookup race: editing the field during a request could display an estimate for the previous value. The request is now invalidated on input, and the invalid, serviceable, and unserviceable outcomes were verified.

## Prompt 3
- Tool: GitHub Copilot
- Type: code
- Prompt:
  > i want to update image like as Assam Breakfast Black Tea,### Darjeeling First Flush,### Kashmiri Kahwa,### Masala Chai Blend,### Nilgiri Green Tea,### Chamomile & Tulsi,### Tea Lover's Sampler Gift Box,### Hibiscus Rose Infusion, i store in file
- Outcome: modified
- Why: Seven matching product images were present. I cropped and optimized them, then mapped them to their product entries. No Hibiscus Rose image was supplied, so its existing image remains in use.

## Prompt 4
- Tool: GitHub Copilot
- Type: code
- Prompt:
  > i want to replace  hero--banner to Mistawale Tea_ A Moment of Calm.png
- Outcome: modified
- Why: The supplied banner included the misspelling "Mistawale" and unsupported claims. I cropped those out, optimized the cup-and-hills image, and updated the page and social preview references.

## Prompt 5
- Tool: GitHub Copilot
- Type: code
- Prompt:
  > check all the code and files and delete unnecessary fi;le
- Outcome: modified
- Why: Removed eight unreferenced placeholder SVGs and eight unreferenced multi-megabyte PNG originals after verifying optimized versions, retained all referenced assets, and corrected outdated assessment notes.

## Prompt 6
- Tool: GitHub Copilot
- Type: code
- Prompt:
  > Fix bugs safety
- Outcome: modified
- Why: Fixed the reproduced coupon eligibility bug by rechecking the discount before populating the checkout contract. Verified both eligible and gift-only checkout payloads.

## Prompt 7
- Tool: GitHub Copilot
- Type: code
- Prompt:
  > Protect assessment requirements
- Outcome: modified
- Why: Replaced the gift-box image that contained a false tea-type label and unsupported packaging claims with a clean, unlabelled SVG illustration. Product facts, API, checkout contract, and legal text remain unchanged.

## Current image update
- The supplied Hibiscus Rose and Tea Lover's Sampler artwork was added after the earlier image prompts and optimized to `images/hibiscus-rose-infusion.jpg` and `images/tea-lovers-sampler-gift-box.jpg`.
- Those current product image references supersede the earlier note that Hibiscus Rose had no supplied artwork and the earlier gift-box SVG replacement. The project retains the optimized JPEG assets, not the source PNG copies; unused legacy SVG placeholders were removed.

## Prompt 8
- Tool: GitHub Copilot
- Type: code
- Prompt:
  > all the data and files chexk and improves the project and delete unnecessary data and iles
- Outcome: modified
- Why: Audited the project files and image references, fixed the compressed mobile search layout, and corrected stale image inventory notes. No files were deleted because every image is used and the other files are project/submission documentation.

## Prompt 9
- Tool: GitHub Copilot
- Type: code
- Prompt:
  > so you all solve problem
- Outcome: modified
- Why: Prepared the required assessment ZIP and verified its contents and size for submission.
