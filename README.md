# Jekyll Uglify Filter

This [Jekyll](https://jekyllrb.com/) plugin creates an `uglify` Liquid Template filter. I use it to minify JavaScript for inlining.

## Installation

1. Add `_plugins/uglify.rb` to your Jekyll site's `_plugins` directory
2. Add this to Jekyll's `_config.yml` file:

  ```
  gems:
    - uglifier
  ```

3. Add `gem "uglifier"` to your Gemfile
4. Run `bundle install`

## Usage

The `uglify` filter runs a string of JavaScript through the Uglifier Gem and returns it. I use it to minify JavaScript for inlining:

```
{% capture scripts %}
  {% include main.js %}
{% endcapture %}
<script>{{ scripts | uglify | strip }}</script>
```
