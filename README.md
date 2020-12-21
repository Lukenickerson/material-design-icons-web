# Material Design Icons for the Web

## Problems

Google's [Material Design Icons](https://material.io/resources/icons/?style=baseline) are beautiful,
but they are lacking a convenient way to integrate the icons into a web project where you want to
**self-host** the icons and are using **npm**.

* Using the fonts with a `<link>` to google (their preferred way) is easy, but it's not always the
solution you want or need.
* Installing via `npm install material-design-icons` pulls in the older 3.x version, rather than 4.x
which includes outlined icons and more.
* Doing an install via `npm install https://github.com/google/material-design-icons` (if it works)
would download *hundreds of MB (nearly a GB!)* - including icons for iOS, Android, and more. This is overkill for
most projects.
* Font files from the repo are in `otf` format rather than the preferred, smaller `woff2` format.
* Downloading the files from the repo and manually copying them over means you're introducing a
manual step for a dependency that should be handled in an automated way. Also you still have to
download hundreds of MB (without [GitZip](https://kinolien.github.io/gitzip/)).

## Solution

The point of this repo is to be small in size, and allow easy integration into your web project.

* Easy to self-host the icons
* Uses the latest fonts from Material Icons 4.0.0
* Files needed to deploy are less than 500 KB (entire repo is less than 2 MB)
* Stylesheets already created for you
* Uses `woff2` ([see woff2 support](https://caniuse.com/woff2); files converted with [CloudConvert](https://cloudconvert.com/otf-to-woff2)), but includes the originals in the `fonts` folder.
* Only one *copy* needed, or no manual step once it is setup using webpack

## How to Use

1. `npm install https://github.com/Lukenickerson/material-design-icons-web`
1. Copy the files from `YOUR_PROJECT/node_modules/material-design-icons-web/web` to wherever you want your material icon files to live, e.g., `YOUR_PROJECT/static/styles/material-icons` -- either manually, or with Webpack (see below), or some other tool.
1. Link to one or more stylesheets from your HTML, e.g., `<link rel="stylesheet" href="static/styles/material-icons/material-icons-outlined.css" />`. See list of css filenames below.
1. Use the [material styling and ligatures](https://google.github.io/material-design-icons/#using-the-icons-in-html)
in your HTML, e.g. `<i class="material-icons-outlined">face</i>`. See class names below.

### Stylesheets and Classes

| Name     | CSS File | CSS Class |
|----------|----------|-----------|
| Filled   | `material-icons-filled.css` | `material-icons` |
| Outlined | `material-icons-outlined.css` | `material-icons-outlined` |
| Rounded  | `material-icons-round.css` | `material-icons-round` |
| Two-Tone | `material-icons-two-tone.css` | `material-icons-two-tone` |
| Sharp    | `material-icons-sharp.css` | `material-icons-sharp` |
| *All*    | `material-icons-all.css` | All of the above |

### Webpack

Use Webpack to copy the files over: 

* Install webpack and the copy plugin: `npm install webpack webpack-cli copy-webpack-plugin`
* Add the apropriate commands to your `webpack.config.js` file.

## Future

* If Google includes woff2 format and comes up with a better solution for developers to pull in the fonts from the 4.x version of the repo, this may no longer be needed.
* If there are other developer-friendly tools that could help web developers (e.g., some way to handle svg icons smartly), they could get added to
this project.

## Material Icon Links

* Material Design Icons: https://material.io/resources/icons/?style=baseline
* Developer guide: https://google.github.io/material-design-icons/
* The repository: https://github.com/google/material-design-icons

## License 

The icons are available from Google under the Apache License Version 2.0.
