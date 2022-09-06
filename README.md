# WovTheme

WovTheme is a theme for [Hugo](https://gohugo.io/) to build OV website.

## Installation

### Add theme for your project

The theme can be retrieve from [Git](https://github.com/reneca/wovtheme.git), with:

```bash
$ git submodule add https://github.com/reneca/wovtheme.git themes/wovtheme
```

or if the project is not versionned

```bash
$ git clone https://github.com/reneca/wovtheme.git themes/wovtheme
```

### Prepare the theme

In order to use less brandwidth, static resources can be forward compressed.
To compress all the theme static files (CSS, images, js)

The command should be execute at the root theme directory:
```bash
$ for file in $(find static -type f -iname '*.css' -or -iname '*.js' -or -iname '*.svg' -or -iname '*.png'); do gzip --best -c $file > $file.gz; done
```

### Use the theme

To use the theme in your project, add the parameter in your `config.toml`:

```toml
theme = "wovtheme"
```

or in your `config.yaml`:

```yaml
theme: wovtheme
```

### Mandatory files

The theme need some file in your project to properly work.

#### CSS

You need to have a css/palette.css with your custom colors:
```css
:root {
  --color-dark-scheme-bg: #1B1D22;
  --color-dark-primary-bg: #303236;
  --color-dark-primary-txt: #eeeeee;
  --color-dark-secondary-bg: #616367;
  --color-dark-secondary-txt: #c0bab6;
  --color-primary: #9c27d9;
}
```

The main color to set is the `--color-primary`. The other are optionnals.

#### Images

The theme use some standard image for logos.
 - _img/wov/icon_back.svg_ use as the website icon
 - _img/wov/logo.svg_ Icon of your header logo (without the text)
 - _img/wov/textlogo.svg_ Text of your header logo
 - _img/wov/tabicon.svg_ Pinned tab icon use in Safari

## Configure

### Params

#### Main parameters

The main parameters are for the site description, author,...

They have to be configure through:
```yaml
params:
  title_short: "WS"
  desc: "Description of the website"
  author: "Name of the author"
  keywords: "keyword, website"
```

#### Socials

You can also set socials for the site:
```yaml
params:
  wov_socials:
  - name: "twitter"
    url: "https://twitter.com/username"
  - name: "github"
    url: "https://github.com/username"
  - name: "dockerhub"
    url: "https://hub.docker.com/r/project"
```

It'll bring socials link to the footer.

### Multilingual

The multilingual can be configure as [Hugo multilingual](https://gohugo.io/content-management/multilingual/).

For now the theme translate:
 - French
 - Español
 - Deutsch
 - English
