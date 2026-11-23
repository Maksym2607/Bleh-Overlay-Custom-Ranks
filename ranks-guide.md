# Custom rank animations and effects

Use one `animation` and one `effect` per player. They work together:

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
| `glow` | A subtle halo around the text |

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

You can omit `animation` or `effect` for `none`. The old animation value
`wave` is not supported; use `dark wave` or `bright wave`.

These settings appear in the custom tab list. The overlay loads ranks from
the GitHub `ranks.json`, not the separate local file in Documents. Older
overlay versions may reject effects they do not support.
