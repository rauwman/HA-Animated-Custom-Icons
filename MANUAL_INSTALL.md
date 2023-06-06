# Changes in tablet.yaml
- copy under state-icon-active-color: "#3182b7" IN YOUR THEME FILE

```
  state-icon-color-transparent: rgba(0,0,0,0)
  state-icon-active-color-bulb: "#ffcc00"
  state-icon-active-color-room: "#3182b7"
  state-icon-active-color-shade: "#3182b7"
  state-icon-active-color-glow: "#ffcc00"

```
![Screenshot](/Main/edit/mod_theme.png)

# Changes in extra_style.yaml

- copy following under --light-color BLOCK 
```
          --bulb-color: ${
            variables.state_on && entity.attributes.brightness
                ? bulb_color
                : variables.state_on && !entity.attributes.brightness
                    ? 'var(--state-icon-active-color-bulb);'
                    : 'var(--state-icon-color);' }

          --room-color: ${
            variables.state_on && entity.attributes.brightness
                ? room_color
                : variables.state_on && !entity.attributes.brightness
                    ? 'var(--state-icon-active-color-room);'
                    : 'var(--state-icon-color);' }

          --shade-color: ${
            variables.state_on && entity.attributes.brightness
                ? shade_color
                : variables.state_on && !entity.attributes.brightness
                    ? 'var(--state-icon-active-color-shade);'
                    : 'var(--state-icon-color);' }

          --glow-color: ${
            variables.state_on && entity.attributes.brightness
                ? glow_color
                : variables.state_on && !entity.attributes.brightness
                    ? 'var(--state-icon-active-color-glow);'
                    : 'var(--state-icon-color-transparent);' }

        }
```

- copy following under .light-color BLOCK

```
        .bulb-color {
          fill: var(--bulb-color);
          transition: all 0.25s ease-out;
        }

        .room-color {
          fill: var(--room-color);
          transition: all 0.25s ease-out;
        }

        .shade-color {
          fill: var(--shade-color);
          transition: all 0.25s ease-out;
        }

        .glow-color {
          fill: var(--glow-color);
          transition: all 0.25s ease-out;
        }

```

![Screenshot](/Main/edit/mod_extra.png)