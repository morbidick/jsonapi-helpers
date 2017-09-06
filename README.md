# Polymer 2 components to communicate with a jsonapi

[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://www.webcomponents.org/element/morbidick/jsonapi-helpers)
[![Build Status](https://travis-ci.org/morbidick/jsonapi-helpers.svg?branch=master)](https://travis-ci.org/morbidick/jsonapi-helpers)

Components to communicate with an api, according to the [jsonapi spec](http://jsonapi.org/format/).

## Components

### \<jsonapi-resource\>

Interact with a jsonapi resource endpoint. Items can be **fetched**, **created**, **updated** and **deleted**.

```html
<jsonapi-resource
  id="getExample"
  api-url="http://example.net"
  resource="books"
  response="{{ my_response }}"
  auto-get
></jsonapi-resource>

<jsonapi-resource
  id="getOneExample"
  api-url="http://example.net"
  resource="books"
  resourceId="1"
  response="{{ my_response }}"
  auto-get
></jsonapi-resource>

<jsonapi-resource
  id="saveExample"
  api-url="http://example.net"
  resource="books"
></jsonapi-resource>
<script>
  let resource = this.$.saveExample;
  resource.data = { title: 'awesome book', author: 'morbidick' };
  resource.save();
</script>
```

### \<jsonapi-settings\>

Set api settings once globally. For now they can't be overwritten on the `jsonapi-resource` element.

```html
<jsonapi-settings
  api-url="http://example.net"
></jsonapi-settings>

<jsonapi-resource
  resource="books"
  response="{{ my_response }}"
  auto-get
></jsonapi-resource>
```

### \<jsonapi-error-toast\>

"Singleton Element" to display a toast with the error details if any `<jsonapi-resource>` on the site encounters an error.

```html
<jsonapi-error-toast></jsonapi-error-toast>
<jsonapi-resource
  resource="undefined_endpoint"
  auto-get
></jsonapi-resource>
```

## Development

```bash
# Get dependencies
$ npm install

# Demo site
$ npm start

# Run tests
$ npm test
```
