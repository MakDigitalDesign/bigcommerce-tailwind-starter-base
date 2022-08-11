Brought to you and maintained by [Trellis Commerce](https://trellis.co/) - A full-service eCommerce agency based in Boston, MA

# Cornerstone + TailWindCSS + Prettier BigCommerce Starter Theme

BigCommerce Cornerstone theme with TailWindCSS &amp; Prettier integrations

The starter theme includes an integration of:

## [TailwindCSS](https://tailwindcss.com/)

- [Configured](https://markustripp.medium.com/extend-shopify-dawn-theme-with-a-custom-tailwind-css-carousel-section-e3efe3ecf18e) to use `prefix: tw-` in order to not clash with Cornerstone's existing styles

## [Trellis' Prettier config](https://www.npmjs.com/package/@trelliscommerce/prettier-config) with Husky pre-commit hooks

- Formats JS, SCSS, & CSS whenever a git commit is made
- Setup your own VSCode to apply Prettier formatting when a file is saved (optional)

## Steps to Start Using this Starter Theme

1. Fork this repository, navigate to the directory, run `npm install`

2. After `npm install` has completed, run `npm run tailwind` to start the Tailwind `--watch` [command](https://tailwindcss.com/docs/installation).

## Stencil Push Your Theme

3. Create an [API token](https://developer.bigcommerce.com/stencil-docs/ZG9jOjIyMDcwMQ-live-previewing-a-theme) with theme publishing permissions

4. To connect to your store, run `stencil init --url https://XXX.mybigcommerce.com --token XXX`

5. To pull down the configuration from the active theme on your live store and updates your local configuration, run `stencil pull`

6. To bundle your theme into a zip file and then push the theme to your BigCommerce store, run `stencil push`

## Common local development commands

1. Before beginning any work, it is good practice to pull down the latest changes from the BigCommerce Cornerstone theme:

```
git fetch upstream
git pull upstream main
```

2. Add upstream link if you get the error `fatal: 'upstream' does not appear to be a git repository` run: `git remote add upstream https://github.com/bigcommerce/cornerstone.git` or `git remote add upstream https://github.com/TrellisCommerce/bigcommerce-cornerstone-tailwind-starter-base.git` depending on which repository you want to pull updates from

3. Anytime you add a TailwindCSS class (remember to prefix it with twcss-), run the CLI tool to scan your template files for classes and build your CSS to assets/app.css:
   `npx tailwindcss -i ./assets/scss/app-tailwind.css -o ./assets/scss/app.scss --watch`

- Run this command in a separate terminal so it will continue to run while you are developing.

## Static assets

Some static assets in the Stencil theme are handled with Grunt if required. This
means you have some dependencies on grunt and npm. To get started:

First make sure you have Grunt installed globally on your machine:

```
npm install -g grunt-cli
```

and run:

```
npm install
```

Note: package-lock.json file was generated by Node version 10 and npm version 6.11.3. The app supports Node 10 as well as multiple versions of npm, but we should always use those versions when updating package-lock.json, unless it is decided to upgrade those, and in this case the readme should be updated as well. If using a different version for node OR npm, please delete the package-lock.json file prior to installing node packages and also prior to pushing to github.

If updating or adding a dependency, please double check that you are working on Node version 10 and npm version 6.11.3 and run `npm update <package_name>` or `npm install <package_name>` (avoid running npm install for updating a package). After updating the package, please make sure that the changes in the package-lock.json reflect only the updated/new package prior to pushing the changes to github.

### Icons

Icons are delivered via a single SVG sprite, which is embedded on the page in
`templates/layout/base.html`. It is generated via a grunt task `grunt svgstore`.

The task takes individual SVG files for each icon in `assets/icons` and bundles
them together, to be inlined on the top of the theme, via an ajax call managed
by svg-injector. Each icon can then be called in a similar way to an inline image via:

```
<svg><use xlink:href="#icon-svgFileName" /></svg>
```

The ID of the SVG icon you are calling is based on the filename of the icon you want,
with `icon-` prepended. e.g. `xlink:href="#icon-facebook"`.

Simply add your new icon SVG file to the icons folder, and run `grunt svgstore`,
or just `grunt`.

#### License

(The MIT License)
Copyright (C) 2015-present BigCommerce Inc.
All rights reserved.

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense,and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
