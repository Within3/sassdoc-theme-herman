# Herman [a SassDoc theme]

> “**If it’s not documented, it doesn't exist.**
> Documentation should become the default,
> an integrated part of the development process.”
>
> <cite>—Miriam Suzanne</cite>

At [OddBird][oddbird],
we wanted better tools for documenting
the entire front end of a project –
from brand guidelines to UX patterns and code APIs:

- Documenting the intersection of languages and styles
- Written directly in the code,
  and integrated with code architecture
- Automated for a document that grows and changes
  along with the life of your project

Herman is built as an extension to [SassDoc][sassdoc],
and supports all their core functionality
for font specimens, color palettes, sizes, SVG icons,
compiled languages, Nunjucks/Jinja macros, HTML previews,
and more.


## Getting Started

```bash
npm install sassdoc sassdoc-theme-herman
```

See the [SassDoc documentation](http://sassdoc.com/getting-started/)
to install SassDoc and run it via various build tools.
Specify `herman` as the theme
in your `sassdocrc` or cli options:

```bash
sassdoc <src> --theme herman
```

Currently,
all SassDoc/Herman annotations are written as Sass comments
starting with `///` to differentiate documentation
from other developer comments (`//`).

  // This comment will be ignored by Herman
  /// This comment will be rendered in the documentation

Annotation comments can be free-floating,
or attached to a particular Sass/CSS object –
such as a variable, mixin, function, or selector block.

  /// this is a free-floating comment

  /// this comment is attached to the following mixin code-block
  @mixin sample-object { … }

In addition to the core SassDoc annotations,
our `@icons` annotation allows you to
display SVG icons from a given folder,
and we provide a `@preview` command
for displaying color-palettes, font-specimens,
text and spacing sizes, and modular ratios.
We also extend the core `@example` annotation
to display compiled Sass/Nunjucks output
and render sample components.

[See the full documentation for details »][docs]

[oddbird]: http://oddbird.net/
[sassdoc]: http://sassdoc.com/
[docs]: http://oddbird.net/herman/docs/


## Additional Herman Options

### customCSS

Type: `String`

Relative path to a custom CSS file, which will be used instead of the default
`theme.css` Herman styles.

### sassjsonfile

Type: `String`

Relative path to a `sass-json file` (created with
https://github.com/oddbird/sass-json-export). The JSON contents will be added
under the `sassjson` key of the sassdoc context, and used to display colors,
fonts, ratios, and sizes.

### templatepath

Type: `String`

*Required if using [`minifiedIcons` option](#minifiedicons), `@icons`
annotation, [`@example` annotation](#rendering-nunjucks-examples) (with
language `njk`), or `@macro` annotation.*

Relative path to a directory containing Nunjucks templates and SVG icons.

### minifiedIcons

Type: `String`

*Requires `templatepath` option.*

Path (relative from the `templatepath` directory) to a file containing minified
SVG icons: one `svg` element with many `symbol` elements, generated by
https://github.com/Hiswe/gulp-svg-symbols or similar. This file will be
included at the top of the generated `body` tag.


## SassDoc Extras

Herman uses a number of SassDoc Extras:

- Description: http://sassdoc.com/extra-tools/#description-description-descriptionpath
- Markdown: http://sassdoc.com/extra-tools/#markdown-markdown
- Display: http://sassdoc.com/extra-tools/#display-toggle-display
- GroupName: http://sassdoc.com/extra-tools/#groups-aliases-groupname
- ShortcutIcon: http://sassdoc.com/extra-tools/#shortcut-icon-shortcuticon
- Sort: http://sassdoc.com/extra-tools/#sort-sort
- ResolveVariables: http://sassdoc.com/extra-tools/#resolved-variables-resolvevariables
