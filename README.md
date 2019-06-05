# MJML Mailchimp

Mailchimp compatible MJML components.

## Usage

```js
const mjmlEngine = require('mjml');
const { registerComponent } = require('mjml-core');
const { registerDependencies } = require('mjml-validator');
const { McSection, McImage, McText, McButton } = require('mjml-mailchimp');

registerComponent(McSection);
registerComponent(McImage);
registerComponent(McText);
registerComponent(McButton);
registerDependencies({
  'mc-section': ['mj-column', 'mj-group', 'mj-raw'],
  'mj-column': ['mc-image', 'mc-text', 'mc-button'],
  'mj-hero': ['mc-image']
});

const template = `
<mjml>
  ...
  <mc-section mc:repeatable="sections" mc:variant="Large Image">
    <mj-column>
      <mc-image mc:edit="Image 01" src="http://placehold.it/600x400">
    </mj-column>
  </mc-section>
  ...
</mjml>
`;

console.log(mjml2html(template));
```
