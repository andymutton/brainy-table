[![Build Status](https://travis-ci.org/web-padawan/brainy-table.svg?branch=master)](https://travis-ci.org/web-padawan/brainy-table)
[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://beta.webcomponents.org/element/web-padawan/brainy-table)

_[Demo and API docs](http://kulikov.pp.ua/brainy-table/)_

# &lt;brainy-table&gt;

`brainy-table` is a Polymer 1.x data table element.

<!--
```
<custom-element-demo>
  <template>
    <script src="../webcomponentsjs/webcomponents-lite.js"></script>
    <link rel="import" href="../iron-ajax/iron-ajax.html">
    <link rel="import" href="brainy-table.html">
    <next-code-block></next-code-block>
  </template>    
</custom-element-demo>
```
-->
```
<template is="dom-bind">
  <iron-ajax auto url="demo/users.json" last-response="{{users}}"></iron-ajax>
  <brainy-table items="[[users.data]]">
    <brainy-table-column name="First Name" filter-by="user.name.first" sort-by="user.name.first">
      <template>[[item.user.name.first]]</template>
    </brainy-table-column>
    <brainy-table-column name="Last Name" sort-by="user.name.last" align-right>
      <template>[[item.user.name.last]]</template>
    </brainy-table-column>
    <brainy-table-column name="Email">
      <template>[[item.user.email]]</template>
    </brainy-table-column>
  </brainy-table>
</template>
```

Inspired by [iron-data-table](https://github.com/Saulis/iron-data-table).
Follows the guidelines of [Material Design](https://material.google.com/components/data-tables.html).

## Features
- Data filtering
- Data sorting
- Template support for each column
- Two-way binding support
- Custom styling support for templates
- Flex support for cells
- Native Shadow DOM support
- Column manipulation, resizing, hiding, reordering
- Custom header templates
- Row details
- Horizontal scrolling shadows
- "Drag-and-drop" scroll

## Special use cases
- Limited amount of data (for infinite scrolling, consider using `iron-data-table` instead)
- Table shouldn't be explicitly sized (height depends on rows count)
- Rows can include dropdown menus etc (no `transform` is used, so table does not create `z-index` trap)
