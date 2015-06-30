# Client Implementation Specifications
_2015-06-01_

### Overview

The client side will be powered by the new Webcomponents standards, with
Google's Polymer used to reduce boiler-plate

### Build
The system aims to fulfill the following when deployed to a production
environment:

- A single file for each type external resources
  - For JS this would be uglified, concat'd file, with both the libs and custom
    code bundled in the correct order (i.e. client code after lib code)
  - For CSS / SCSS they should be optionally compiled, parsed, and then
    concat'd into a single `style.css`. Again order is important
  - For `.html` imports, these should be _vulcanised_ into a single file and
    then imported via a `link rel="import"`

The justifaction for this is that it cuts down the number of requests that need
to be executed before page load. We want to limit ourselves to a single request
for each file.

### Build sources and destinations
Where should these libraries be built into?
We currently have three folders in `src` and one in the project root:
- `bower_components` Contains all the lib code imports (in the root)
- `scripts` Contains all out our client side JS
- `styles` Contains all our customs styles
- `templates` Contains all of the templates for various components

How should we build them
- `JavaScripts`: collect the main's out of bower, then concat into
  `public/scripts.js` along with our source JS
- `CSS / SCSS` bower, compile, concat into `styles.css`
- `templates / Webcomponents` compile and concat into an `imports.html`
