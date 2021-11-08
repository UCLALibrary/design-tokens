# UCLA Library Design Tokens

Design tokens for UCLA Library.

The **Design Tokens** repository stores and syncs design tokens from the UCLA Library Design System using the [Figma Tokens plugin](https://docs.tokens.studio/) and GitHub Actions to generate Sass variables for use. 

## What are Design Tokens?

> Design tokens are the visual design atoms of the design system — specifically, they are named entities that store visual design attributes. We use them in place of hard-coded values (such as hex values for color or pixel values for spacing) in order to maintain a scalable and consistent visual system for UI development. - [Salesforce UX](https://www.lightningdesignsystem.com/design-tokens/)

Helpful Explainers:
- [Smashing Podcast, Episode 3: What are Design Tokens? with Jina Anne](https://www.smashingmagazine.com/2019/11/smashing-podcast-episode-3/)
- [Tokens in Design Systems by Nathan Curtis](https://medium.com/eightshapes-llc/tokens-in-design-systems-25dd82d58421)

## Usage

TBD

## Files

- `data/tokens.json` - Syncs with Figma Tokens plugin
- `data/transformed-tokens.json` - Tokens transformed to be usable by Style Dictionary
- `scss/variables.scss` - Tokens usable by developers

## Best Practices

Helpful reminders to future selves:
- Branch name should use snake case (e.g., update_readme)
- Always leave a comment when creating, reviewing, and merging a pull request