# svg-wrapper element

You can wrap your SVGs if it contains style tags just by replacing them with svg-style.
Alternatively provide the svg-data property as a string with actual SVG data. You can also
bind to this property but the textContent inside the element is not bindable.

Setting `pre-render` property will draw the SVG onto a canvas to prevent any further SVG draw operations to improve performance.

If you provide a unique reference property, consequent wrappers with same reference will display the same image with same size, without re-drawing anything.

When using `pre-render`;

The element will trigger `renderCompleted` when the SVG is successfully drawn.
The element will trigger `renderStart` when the SVG has started drawing.

These two events are expected to trigger with equal amounts if no errors occur, so you can keep track of waiting and rendered SVGs.

## Installation

bower install svg-wrapper

## Usage

    <svg-wrapper
        pre-render="true">
        <svg width="100%"><defs><svg-style>[These will not affect current scope's style]</svg-style> ... </svg>
    </svg-wrapper>

    <svg-wrapper
        pre-render="true"
        svg-data='<svg width="100%"><defs><style>[You can use regular style tag with svg-data]</style> ... </svg>'>
    </svg-wrapper>

    <svg-wrapper
        pre-render="true"
        reference="myUniqueId"
        svg-data='<svg width="100%"><defs><style>[You can use regular style tag with svg-data]</style> ... </svg>'>
    </svg-wrapper>

    <!-- This won't need data, will display the above image -->
    <svg-wrapper
        reference="myUniqueId"
    </svg-wrapper>

    <svg-wrapper
        svg-data='<svg width="100%"><defs><svg-style>[These will not affect current scope's style]</svg-style> ... </svg>'>
    </svg-wrapper>

    <svg-wrapper>
        <svg width="100%"><defs><svg-style>[These will not affect current scope's style]</svg-style> ... </svg>
    </svg-wrapper>

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

### Trying out the element

First, make sure you have the [Polymer CLI](https://www.npmjs.com/package/polymer-cli) installed. Then run `polymer serve` to serve this element locally.

## Credits

Ali Naci Erdem
https://alinacierdem.com
Support me at http://patreon.com/anacierdem