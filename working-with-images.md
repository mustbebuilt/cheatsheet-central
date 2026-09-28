# Web Images Cheat Sheet

## 1. Choose the right image format

| Format         | Best for                | Typical use                            |
| -------------- | ----------------------- | -------------------------------------- |
| **JPEG / JPG** | Photographs             | Photos, banners, backgrounds           |
| **PNG**        | Graphics + transparency | Logos, icons, screenshots              |
| **WebP**       | Photos + graphics       | **Good default for modern websites**   |
| **AVIF**       | Photos + graphics       | Excellent compression; modern browsers |
| **SVG**        | Vector graphics         | Logos, icons, diagrams                 |
| **GIF**        | Simple animation        | Avoid for normal photographs           |

**Rule of thumb:** Use **WebP** for most photographic web images, **SVG** for logos/icons, and **PNG** where transparency or lossless quality is important.

---

## 2. Don't upload the original camera image

A modern camera/phone may produce:

```text
6000 × 4000 pixels
8–15 MB
```

A website might only display it at:

```text
1200 × 800 pixels
100–300 KB
```

**Resize first, then optimise.**

> There is little benefit in sending a 6000px image to a browser when it will only be displayed at 1200px.

---

## 3. Suggested web image sizes

| Purpose                | Suggested maximum width |
| ---------------------- | ----------------------: |
| Small thumbnail        |              300–500 px |
| Card / product image   |              600–800 px |
| Content image          |            1000–1400 px |
| Large banner           |            1600–2000 px |
| Full-screen/hero image |            2000–2400 px |

These are **starting points**, not hard rules. Check how large the image actually appears on the page.

---

## 4. Target file sizes

| Image                |             Target |
| -------------------- | -----------------: |
| Small icon/thumbnail |           < 100 KB |
| Normal web image     |     **100–300 KB** |
| Large/hero image     |     **200–500 KB** |
| Very large image     | Try to stay < 1 MB |

**Smaller is generally better** — provided the image still looks good.

---

## 5. Resize vs compress

### Resize

Changes the **pixel dimensions**:

```text
6000 × 4000
       ↓
1200 × 800
```

### Compress / optimise

Reduces the **file size** without necessarily changing dimensions:

```text
1200 × 800
2.5 MB → 180 KB
```

For web use, you will often want to do **both**.

---

## 6. Image quality

For JPEG/WebP:

```text
Quality 60–80%
```

is often a good starting point.

Compare the result visually rather than automatically choosing maximum quality.

---

## 7. Useful tools

### Online tools

- **[Squoosh](https://squoosh.app/)** — resize, compress and compare formats
- **[TinyPNG](https://tinypng.com/)** — quick PNG/WebP optimisation
- **[TinyJPG](https://tinyjpg.com/)** — JPEG optimisation
- **[iLoveIMG](https://www.iloveimg.com/)** — resize and compress batches of images

### Desktop tools

- **[ImageMagick](https://imagemagick.org/)** — powerful command-line image processing
- **[GIMP](https://www.gimp.org/)** — free image editor (available through AppsAnywhere)
- **[Adobe Photoshop](https://www.adobe.com/products/photoshop.html)** — professional editing and export

---

## 8. A practical workflow

```text
Camera / Phone / Original
          ↓
        CROP
          ↓
       RESIZE
          ↓
   Convert to WebP
          ↓
      OPTIMISE
          ↓
    Check quality
          ↓
       WEBSITE
```

### Example

```text
6000 × 4000 JPEG
       8 MB
        ↓
1200 × 800 WebP
      180 KB
```

**Result:** A dramatically smaller download with an image that may look virtually identical on a normal webpage.

---

## 9. Remember: HTML/CSS doesn't resize the download

This:

```html
<img src="large-photo.jpg" width="600" />
```

may display the image at **600px wide**, but the browser can still have to download the entire original image.

**Resize the actual image file**, not just its display dimensions.

### ⭐ Web design rule

> **Serve an image close to the size at which it will actually be displayed.**
