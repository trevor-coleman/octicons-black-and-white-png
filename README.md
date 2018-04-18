# render-octicons

`render-octicons` is a bash script that uses rsvg-convert to render png versions of the octicons in various colours.

## Installation

**1. Clone this repository:**

`git clone git@github.com:trevor-coleman/render-octicon-colors.git`

**2. Install packages**

`yarn` or `npm install`

**3. Install lib2rsvg**

`sudo apt-get install librsvg2-bin`

## Usage

`render-octicons x11color [options] [rsvg-convert options]`

### Examples

| Command                                          | Path                                       |                                                                Image                                                                |
| ------------------------------------------------ | ------------------------------------------ | :---------------------------------------------------------------------------------------------------------------------------------: |
| `./render-octicons green`                        | `./green/alert-green.png`                  |           ![green alert](https://github.com/trevor-coleman/render-octicons/blob/master/examples/alert-green.png?raw=true)           |
| `./render-octicons aquamarine --size 100`        | `./aquamarine-100px/beaker-aquamarine.png` |     ![aquamarine beaker](https://github.com/trevor-coleman/render-octicons/blob/master/examples/beaker-aquamarine.png?raw=true)     |
| `./render-octicons indigo --size 20 --tag small` | `./indigo-20px/file-submodule-small.png`   | ![small yellow submodule](https://github.com/trevor-coleman/render-octicons/blob/master/examples/file-submodule-small.png?raw=true) |

### Arguments and option

#### REQUIRED ARGUMENTS:

| Argument   | Type   | Description                                                           |
| ---------- | ------ | --------------------------------------------------------------------- |
| `x11color` | String | The name of a colour using x11 color names (e.g. 'red', 'aquamarine') |

#### OPTIONS:

| Argument  |  Type  | Description                                                                                                                                                                        |
| :-------- | :----: | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| -t --tag  | string | appends string to output filename arrow.svg --> arrowstring.png. Defaults to `-{x11color}`                                                                                         |
| -s --size | number | simple sizing - sets width to number in pixels, keep aspect ratio. Defaults to 300px. When using this option, files will output to `./{x11color}-{size}px` (e.g. `./orange-500px`) |
| --dir     |  path  | output files to path. will create directory if it doesn't exist.                                                                                                                   |

#### RSVG-CONVERT OPTIONS:

    NOTE: If using rsvg-convert options, you must specify an output directory

| Argument                        |                          Type                          | Description                                                                                                           |
| :------------------------------ | :----------------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------- |
| `-d`<br> `--dpi-x`              |                         number                         | Set the X resolution of the image in pixels per inch. RSVG's current default is 90dpi                                 |
| `-p`<br/> `--dpi-y`             |                         number                         | Set the Y resolution of the image in pixels per inch. RSVG's current default is 90dpi                                 |
| `-x`<br/> `--x-zoom`            |                         number                         | X Zoom factor, as a percentage. If unspecified, 1.0 is used as the default.                                           |
| `-y`<br/> `--y-zoom`            |                         number                         | Y Zoom factor, as a percentage. If unspecified, 1.0 is used as the default.                                           |
| `-z`<br/> `--zoom`              |                         number                         | Zoom factor, as a percentage. If unspecified, 1.0 is used as the default.                                             |
| `-w`<br/> `--width`             |                        integer                         | Specify how wide you wish the image to be. If unspecified, the natural width of the image is used as the default.     |
| `-h`<br/> `--height`            |                        integer                         | Specify how tall you wish the image to be. If unspecified, the natural height of the image is used as the default.    |
| `-f`<br/> `--format`            | `png`, `pdf`,<br/> `ps`, `svg`,<br> `xml`, `recording` | Specify the output format you wish the image to be saved in. If unspecified, PNG is used as the default.              |
| `-a`<br/> `--keep-aspect-ratio` |                                                        | Specify that the aspect ratio is to be preserved. If unspecified, aspect ratio will not be preserved.                 |
| `-b`<br/> `--background-color`  |                         string                         | Specify the background color. If unspecified, the default is transparent. e.g, `black,` `white`, `#abccee`, `#aaa`... |
