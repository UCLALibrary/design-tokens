# UCLA Library Design Tokens

Design tokens for UCLA Library.

The **Design Tokens** repository stores and syncs design tokens from the UCLA Library Design System using the [Figma Tokens plugin](https://docs.tokens.studio/) and GitHub Actions to generate Sass variables for use. 

## What are Design Tokens?

> Design tokens are the visual design atoms of the design system — specifically, they are named entities that store visual design attributes. We use them in place of hard-coded values (such as hex values for color or pixel values for spacing) in order to maintain a scalable and consistent visual system for UI development. - [Salesforce UX](https://www.lightningdesignsystem.com/design-tokens/)

Helpful Explainers:
- [Smashing Podcast, Episode 3: What are Design Tokens? with Jina Anne](https://www.smashingmagazine.com/2019/11/smashing-podcast-episode-3/)
- [Tokens in Design Systems by Nathan Curtis](https://medium.com/eightshapes-llc/tokens-in-design-systems-25dd82d58421)

## Requirements
This package requires [Dart Sass](https://sass-lang.com/dart-sass) because [LibSass is deprecated](https://sass-lang.com/blog/libsass-is-deprecated). If you are using the [node-sass](https://www.npmjs.com/package/node-sass) package in your project (which provides the Node.js binding to the deprecated LibSass), please replace it with the [sass](https://www.npmjs.com/package/sass) package:
```
npm uninstall node-sass && npm install sass --save-dev
```

## Usage
Install the package:
```
npm install ucla-library-design-tokens --save-dev
```
Then in your Sass, load the module (e.g., variables, typography, spacing, or helpers):
```
@import "~ucla-library-design-tokens/scss/variables.scss";
@import "~ucla-library-design-tokens/scss/typography.scss";
@import "~ucla-library-design-tokens/scss/spacing.scss";
@import "~ucla-library-design-tokens/scss/helpers.scss";
```
### Custom Fonts
To use Karbon and Proxima Nova, import `ucla-library-design-tokens/scss/fonts.scss` once at the global level. For example, in the component library add to the configs (vue-cli, webpack, and rollup).
### Variables
Include the desired variable:
```
:root {
  --color-primary-yellow-01: #{$primary-yellow-01}; // SCSS interpolation syntax needed
}

.category {
  margin-bottom: $component-06 + px; // Using SCSS variable
  color: var(--color-primary-blue-03); // Using CSS variable
}
```
### Mixins
Include the desired mixin:
```
.category {
  @include overline;
}
```
### SVGs
Include the desired SVG:
```
import SvgHatchRight from "ucla-library-design-tokens/assets/svgs/graphic-hatch-lines.svg"
```
## Updating to the latest package
Latest release is posted in this repository, but you can also check if your package is outdated: 
```
npm outdated
```
If you are not running the latest release and would like to, then update the package:
```
npm install ucla-library-design-tokens@latest
```
Or, you can update the version number in the `package.json` file and run `npm install`.

## Files

- `data/tokens.json` - Syncs with Figma Tokens plugin
- `data/transformed-tokens.json` - Tokens transformed to be usable by Style Dictionary
- `scss/*` - Tokens usable by developers
- `assets/*` - Assets usable by developers

## Best Practices

Helpful reminders to future selves:
- Use the commit message conventions that trigger [semantic releases](https://semantic-release.gitbook.io/semantic-release/support/faq#how-can-i-change-the-type-of-commits-that-trigger-a-release)
  - feat: A new feature
  - fix: A bug fix
  - docs: Documentation only changes
  - style: Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc)
  - refactor: A code change that neither fixes a bug nor adds a feature
  - perf: A code change that improves performance
  - test: Adding missing or correcting existing tests
  - chore: Changes to the build process or auxiliary tools and libraries such as documentation generation
- Always leave a comment when creating, reviewing, and merging a pull request
- When a new release is published, update dependent apps to use the latest, non-breaking version. If the released package is a major version (has breaking changes), then create appropriate tickets for dependent apps to update the design tokens package.
  - [UCLA Library Website Components](https://github.com/UCLALibrary/ucla-library-website-components/blob/main/package.json#L90)
  - [Library Website Nuxt](https://github.com/UCLALibrary/library-website-nuxt/blob/main/package.json#L42)
  - [MEAP Website Nuxt](https://github.com/UCLALibrary/meap-website-nuxt/blob/main/package.json#L44)
