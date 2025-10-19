# examples


---


1. ️⃣ Basic Shield Syntax

* A GitHub badge is just an image with a link in Markdown:

	[![Alt Text](Image URL)](Link URL)

> Alt Text → This is the text shown if the image doesn’t load.
> Image URL → URL for your badge image (we’ll use shields.io
> to create custom badges).

* Link URL → Where clicking the badge goes.


**Example:**

[![Config Tables](https://img.shields.io/badge/Tables-Config%20Data-orange?style=for-the-badge)](tables/README.md)


> Alt Text: Config Tables
> Image URL: https://img.shields.io/badge/Tables-Config%20Data-orange?style=for-the-badge
> Link URL: tables/README.md → this goes to the tables README in your repo.

---

2. ️⃣ Customizing the badge via Shields.io

> You can go to https://shields.io/
> to create a custom badge.

* Options:

> Label → Text on the left side of the badge (Tables)
> Message → Text on the right side (Config Data)
> Color → Any color you like (orange, blue, green, or hex #8A2BE2)
> Style → for-the-badge (big rectangle), flat, flat-square, plastic, etc.
> Shields.io will generate a URL like:

https://img.shields.io/badge/Tables-Config%20Data-orange?style=for-the-badge

---

# 💡 Tip: Spaces must be %20 in URLs.

3. ️⃣ Adding a link to your badge

* Wrap the image in []() like this:

[![Tables Badge](https://img.shields.io/badge/Tables-Config%20Data-orange?style=for-the-badge)](tables/README.md)


* Clicking the badge now goes straight to tables/README.md in your repository.

Exactly! That’s the correct format. Here’s what each part does:

* [![Tables Badge](https://img.shields.io/badge/Tables-Config%20Data-orange?style=for-the-badge)](LINK)
* [![Tables Badge](...)] → This is the badge image itself.
* (LINK) → This is where clicking the badge will take the user. Replace LINK with a URL or file path.

Examples:

1. ️⃣ Link to a file in your repo:

**[![Tables Badge](https://img.shields.io/badge/Tables-Config%20Data-orange?style=for-the-badge)](tables/README.md)


Clicking goes to tables/README.md in your repository.

2. ️⃣ Link to a section in the same README:
* [![Overview Badge](https://img.shields.io/badge/Overview-Docs-9b59b6?style=for-the-badge)](#overview)

> Clicking jumps to the ## Overview section in your README.

3. ️⃣ Link to an external website:
* [![Discord](https://img.shields.io/badge/Discord-Join%20Us-5865F2?logo=discord&logoColor=white&style=for-the-badge)](https://discord.gg/YOURINVITE)


### Clicking opens the Discord invite in a browser.
