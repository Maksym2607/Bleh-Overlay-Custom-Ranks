# Custom rank animations and effects

Use one `animation` and one `effect` per player. They work together:

- `animation` controls the text's color or glow.
- `effect` controls the text's movement, reveal, or visibility.

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
| `fire` | Red, orange, and yellow flicker across the text |
| `ice` | A cool blue-and-white shimmer |
| `gold rush` | A bright highlight sweeps across gold text |
| `neon glow` | White text with a colored outline and soft halo |

`holographic`, `fire`, `ice`, and `gold rush` use their own colors rather than `color`.

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
| `typewriter` | Letters appear one by one, pause, then erase at the same speed before repeating |
| `bounce` | The whole text gently hops |
| `slide` | Letters slide up into place one by one, pause, then restart |
| `jitter` | Letters move in quick, small random-looking steps |
| `fade` | The whole text fades in and out |
| `scramble` | Random-looking characters settle into the real text, then repeat |
| `blink` | The whole text periodically disappears and reappears |

For the `neon glow` animation, `color` sets the outline color. It can be
combined with any text effect. For example:

```json
{
  "_Maksym": {
    "rank": "[BLEH]",
    "color": "red",
    "animation": "neon glow",
    "effect": "text wave"
  }
}
```

Only one animation can be selected, so `holographic` and `neon glow` cannot
be used together.

## Colors

Use a hex color such as `"#FF5555"`, or one of:

`red`, `dark_red`, `gold`, `yellow`, `green`, `dark_green`, `aqua`,
`blue`, `dark_blue`, `purple`, `pink`, `white`, `gray`, `dark_gray`.

You can omit `animation` or `effect` for `none`. The old animation value
`wave` is not supported; use `dark wave` or `bright wave`. The old
`"animation": "glow"` and `"effect": "neon glow"` values are not supported.
Update every affected entry in GitHub's `ranks.json` to use
`"animation": "neon glow"`; one unsupported value rejects the entire file.

These settings appear in the custom tab list. The overlay loads ranks from
the GitHub `ranks.json`, not the separate local file in Documents. Older
overlay versions reject files containing animations or effects they do not
support. The Bed Wars results chat shows a static approximation of your rank
color; it does not display animations or text effects.
