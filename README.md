# TextGen

- For non-developers
- Component -- Embeddable/extensible like Comicgen
- Only text, not charts

## TextGen is a HTML component

Add this to your page to generate text from data.

`<text-gen ...attrs...></text-gen>`

## Features

- [x] Data: table -> metrics
  - Including Priorities
  - Entities are attributes
  - Calibrations are attributes, supported by lookup functions
- [xx] Templates with weights
- [x] Grammar: npm/humanize

## Component Design

```html
<text-gen temp="Temperature" cases="Covid cases" calibration_table1="{
  'almost sure': -1,
  ...
}" data="{...}">
  <% /* Run pre-processing */ %>
  <template weight="40">When {temp} {calibration(calibration_table1, value)} increases the chances of {cases} {H24} are {H25}</template>
  <template weight="30">=G30&" for "&G29&" is "&K16&" than "&G28</template>
  <template weight="30">="In "&G29&", "&G30&" is "&K16&" than "&G28</template>
</text-gen>
```

## Research NLG engines
