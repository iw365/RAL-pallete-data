# RAL Colour Palette JSON Data

This repo contains colour data for the [RAL colour palette](https://www.ralcolorchart.com/ral-colors) in json format.

## Palettes Included

- [RAL Classic](https://www.ralcolorchart.com/ral-classic) - 216 colours
- [RAL Design](https://www.ralcolorchart.com/ral-design) - 1825 colours
- [RAL Effect](https://www.ralcolorchart.com/ral-effect) - 490 colours
- [RAL Plastics P1](https://www.ralcolorchart.com/ral-plastics-p1) - 100 colours
- [RAL Plastics P2](https://www.ralcolorchart.com/ral-plastics-p1) - 200 colours*
- RAL Complete - 2831 colours, a combination of all the above palettes into a single json file

*RAL Plastics P2 contains duplicate colours, these are transparent colours and are indicated by the -P-T suffix in the RAL colour code.

## File Structure Variations

- `categorised` - Colours are categorised by colour group, as indicated by the subheadings on the respective colour palette pages. For example, [the RAL Classic page](https://www.ralcolorchart.com/ral-classic) has subheadings such as "Yellow hues", "Orange hues", etc.
- `uncategorised` - Colours are not categorised by colour group they are all listed as a single series.
- `rounded` - values for colour data are rounded, see below.

### Rounded Values

- **Luminance** - Rounded to 2 decimal places
- **RGB** - Rounded to the nearest integer
- **CYMK** - Rounded to the nearest integer
- **HSV** - Rounded to the nearest integer
- **HSL** - Rounded to the nearest integer

## Data Stored

- `"name"` - The name of the colour indicated on the colours page.
  - RAL Effect colours are not named.
- `"hex"` - The hex value of the colour.
  - This colour is pulled from the ```background-color``` css property of the colour swatch on the colours grid.
- `"luminance"` - The luminance value of the colour.
    - This is calculated from the RGB values using the formula: ```0.2126 * R + 0.7152 * G + 0.0722 * B``` and is divided by 255 to normalise the value between 0 and 1.
    - This basically indicates the relative brightness of the colour.
    - This is useful for determing whether to use black or white text on top of the colour (black text on colours with a luminance value > 0.5, white text on colours with a luminance value < 0.5 is my general rule of thumb).
- `"rgb"` - The RGB (Red, Green, Blue) components of the colour.
  - RGB values are in the range 0-255.
- `"cymk"` - The CYMK (Cyan, Yellow, Magenta, Black) components of the colour.
  - CYMK values are in the range 0-100%.
- `"hsv"` - The HSV (Hue, Saturation, Value) components of the colour.
  - Hue is in the range 0-360°, Saturation and Value are in the range 0-100%.
  - Saturation is the intensity of the colour - 0% is grey, 100% is full colour.
  - Value is the brightness of the colour - 0% is black, 100% is full brightness.
- `"hsl"` - The HSL (Hue, Saturation, Lightness) components of the colour.
  - This is similar to HSV
  - Lightness is a range from 0-100%, 0% is black, 100% is white, 50% is the midpoint where the colour is at its purest.

## Other Notes

This data was scraped from the corresponding colour palette pages on the [RAL Colour Chart](https://www.ralcolorchart.com/ral-colors) website.

Due to the size of the data I have not checked every single colour, so there may be some errors in the data, but I dont think there will be as the system doesn't change and the data I have checked looks good.

Not every colour system has a one-to-one correspondence with the others, so some values may not be exactly the same across all systems, but they will be as close as possible.

Feel free to raise an issue if you find something that seems off.

Cheers!