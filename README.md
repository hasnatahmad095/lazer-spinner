# 3D Dot Cube Preloader

A lightweight, pure **HTML + CSS** preloader. A 3D cube made of tiny dots
spins slowly in the middle of the screen, with your logo in the centre. No
JavaScript, no libraries and no images.

## Features

- **Pure CSS animation.** It's smooth and light, and it doesn't use JavaScript.
- **3D effect.** Built from 11 layers of dots spaced through the cube's depth.
- **Logo slot.** Swap in your own SVG logo.
- **Webflow friendly.** The markup uses `w-embed` blocks, so you can paste it
  straight into a Webflow **Embed** element.
- **Single file.** Everything lives in `index.html`.

## Quick Start

1. **Clone the repository**

   ```bash
   git clone https://github.com/yourusername/your-repo-name.git
   cd your-repo-name
   ```

2. **Open `index.html` in your browser.**

> **Note:** The dots are white, so the preloader needs a dark background.
> Add this to the styles if your page is light:
>
> ```css
> body { margin: 0; background: #000; }
> ```

## Customisation

| What to change | Where | Example |
| --- | --- | --- |
| Logo | The `<svg>` inside the first `.w-embed` | Replace it with your own SVG |
| Logo colour | `fill` on the `<path>` | `fill="#FF00C5"` |
| Dot colour | `.mod .cube .faces .dot` → `background` | `#ffffff` |
| Dot size | `.dot` → `width` / `height` | `2px` |
| Spin speed | `.mod .cube` → `animation` | `9000ms` (lower is faster) |
| Cube size | `.cube` and `.faces` → `width` / `height` / margins | `210px` |
| Depth / perspective | `.mod` → `perspective` | `330px` |

If you change the cube size, keep the numbers in step with each other.
The margins and `transform-origin` should be half the cube size, and the
`translateZ` values for `.f1` to `.f11` should run from minus half the size to
plus half the size.

## How It Works

- `.mod` sets up the 3D space with `perspective`.
- `.cube` holds 11 flat layers (`.faces`), each pushed to a different depth
  with `translateZ`.
- Each layer has a grid of dots (`.p1` to `.p13`). Layers alternate between a
  9-dot and a 4-dot grid, which creates the lattice pattern.
- The `spinCube` keyframes rotate the whole cube on all three axes in a loop.

## Using It as a Real Preloader

To hide the preloader once the page has loaded, add an `id` to the wrapper and
a short script:

```html
<div class="preload-wrapper" id="preloader">…</div>

<script>
  window.addEventListener("load", () => {
    document.getElementById("preloader").style.display = "none";
  });
</script>
```

## Project Structure

```
├── index.html   # Markup and styles
└── README.md
```

## Browser Support

Works in all modern browsers (Chrome, Edge, Safari and Firefox).

## Contributing

Contributions are welcome. Feel free to open an issue or a pull request.

## License

Released under the [MIT License](LICENSE).

---

## Author

Built and maintained by [Hasnat Ahmad](https://www.devhasnatahmad.com/). Need help with a project? [Get in touch](https://www.devhasnatahmad.com/).

If this project saved you time, please give it a ⭐ on GitHub.
