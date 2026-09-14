# art

Full-resolution originals for the art on [xevrion.dev/art](https://xevrion.dev/art).

The site serves compressed WebP copies so pages load fast. This repo holds the
real files — full resolution, untouched — so anything on the site can always be
downloaded at source quality.

## Layout

```
<slug>/full.png     the original, exactly as exported
```

One folder per piece. The slug matches the entry in the portfolio's
`constants/art.json`.

## Links

Files are linked from the site through jsDelivr rather than GitHub directly:

```
https://cdn.jsdelivr.net/gh/xevrion/art@main/<slug>/full.png
```

jsDelivr is a CDN that serves straight from this repo. `raw.githubusercontent.com`
works too, but it is meant for occasional fetches and throttles under real
traffic — the CDN does not, and caches at the edge.

## Adding a piece

Originals are imported from the portfolio repo, which generates the web copy at
the same time:

```
scripts/add-art.sh <slug> ~/path/to/artwork.png
```

That writes the original here and the compressed copy there, so the two never
drift apart.
