Performance optimizations

Overview
- Consolidated Google Fonts requests into a single stylesheet and added preconnect/dns-prefetch to reduce font load latency.
- Set fetch priority for the above-the-fold hero image and preloaded it on the home page.
- Enabled lazy-loading and async decoding for non-critical images across all pages to reduce initial bytes and speed up first render.

Changes
- index.html
  - Added preconnect/dns-prefetch for Fonts API and consolidated font families into one URL.
  - Preloaded hero image `cocos.png` and set `fetchpriority="high"` on the hero `<img>`.
  - Set `loading="lazy"` and `decoding="async"` on non-critical images; kept header/hero images as high priority.
- produse.html
  - Added preconnect/dns-prefetch for Google Fonts and consolidated fonts.
  - Marked all product images as `loading="lazy"` and `decoding="async"`.
  - Marked the header logo image as `loading="lazy"` and `decoding="async"`.
- about.html
  - Added preconnect/dns-prefetch for Google Fonts and consolidated fonts.
  - Marked the biography image as `loading="lazy"` and `decoding="async"`.

Recommendations (next steps)
- Convert large JPG/PNG images to modern formats (AVIF/WebP) and provide `srcset`/`sizes` for responsive images.
- Specify explicit `width` and `height` attributes on images to eliminate layout shifts.
- If hosting on a CDN, enable caching and compression (gzip/br) and long cache lifetimes for static assets.
- Inline minimal critical CSS or use a critical CSS tool if initial render still lags on slow networks.

