# Custom rank animations and effects

Use one `animation` and one `effect` per player. They work together:

- `animation` controls the text's color or glow.
- `effect` controls the text's movement, reveal, or outline.

```json
{
  "_Maksym": {
    "rank": "[OWNER]",
    "color": "red",
    "animation": "dark wave",
    "effect": "shake"
  }
}
```

## Animations

| Value | Appearance |
| --- | --- |
| `none` | Solid color |
| `dark wave` | A wave between the rank color and a darker shade |
| `bright wave` | A wave between the rank color and a lighter shade |
| `pulse` | The whole name brightens and dims |
| `gradient wave` | A moving wave between `color` and `color2` |
| `shimmer` | A bright highlight sweeps across the text |
| `holographic` | Pastel rainbow colors move across the text |
| `glow` | A subtle halo around the text |

`holographic` uses its own rainbow colors rather than `color`.

`gradient wave` needs a second color:

```json
{
  "_Maksym": {
    "rank": "[OWNER]",
    "color": "red",
    "color2": "blue",
    "animation": "gradient wave",
    "effect": "ripple"
  }
}
```

## Text effects

| Value | Appearance |
| --- | --- |
| `none` | Stationary text |
| `text wave` | Letters move up and down in a continuous wave |
| `shake` | Letters wobble independently |
| `ripple` | A bounce travels across the text, then pauses |
| `typewriter` | Letters appear one by one, pause, then repeat |
| `neon glow` | White text with a colored outline and soft halo |

For `neon glow`, `color` sets the outline color. The selected animation
animates the outline while the text stays white. For example:

```json
{
  "_Maksym": {
    "rank": "[BLEH]",
    "color": "red",
    "animation": "none",
    "effect": "neon glow"
  }
}
```

To make the outline change through holographic colors, use
`"animation": "holographic"` instead of `"none"`.

## Colors

Use a hex color such as `"#FF5555"`, or one of:

`red`, `dark_red`, `gold`, `yellow`, `green`, `dark_green`, `aqua`,
`blue`, `dark_blue`, `purple`, `pink`, `white`, `gray`, `dark_gray`.

You can omit `animation` or `effect` for `none`. The old animation value
`wave` is not supported; use `dark wave` or `bright wave`.

These settings appear in the custom tab list. The overlay loads ranks from
the GitHub `ranks.json`, not the separate local file in Documents. Older
overlay versions reject files containing animations or effects they do not
support. The Bed Wars results chat shows a static approximation of your rank
color; it does not display animations or text effects.
