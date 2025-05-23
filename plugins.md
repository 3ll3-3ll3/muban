# List of Plugins

## Full text search

By default, the hyperlink on the current page is recognized and the content is saved in `IndexedDB`. You can also specify the path to the files.

<!-- prettier-ignore -->
```html
<script>
  window.$docsify = {
    search: 'auto', // default

    search: [
      '/',            // => /README.md
      '/guide',       // => /guide.md
      '/get-started', // => /get-started.md
      '/zh-cn/',      // => /zh-cn/README.md
    ],

    // Complete configuration parameters
    search: {
      // Location in sidebar (default: prepended as first child)
      // Optionally specify insertAfter or insertBefore (not both)
      insertAfter: '.app-name', // CSS selector in .sidebar scope
      insertBefore: '.sidebar-nav', // CSS selector in .sidebar scope

      maxAge: 86400000, // Expiration time, the default one day
      paths: [], // or 'auto'
      placeholder: 'Type to search',

      // Localization
      placeholder: {
        '/zh-cn/': '搜索',
        '/': 'Type to search',
      },

      noData: 'No Results!',

      // Localization
      noData: {
        '/zh-cn/': '找不到结果',
        '/': 'No Results',
      },

      // Headline depth, 1 - 6
      depth: 2,

      hideOtherSidebarContent: true, // Deprecated as of v5

      // To avoid search index collision
      // between multiple websites under the same domain
      namespace: 'website-1',

      // Use different indexes for path prefixes (namespaces).
      // NOTE: Only works in 'auto' mode.
      //
      // When initialiazing an index, we look for the first path from the sidebar.
      // If it matches the prefix from the list, we switch to the corresponding index.
      pathNamespaces: ['/zh-cn', '/ru-ru', '/ru-ru/v1'],

      // You can provide a regexp to match prefixes. In this case,
      // the matching substring will be used to identify the index
      pathNamespaces: /^(\/(zh-cn|ru-ru))?(\/(v1|v2))?/,
    },
  };
</script>
<script src="//cdn.jsdelivr.net/npm/docsify@5/dist/docsify.min.js"></script>
<script src="//cdn.jsdelivr.net/npm/docsify@5/dist/plugins/search.min.js"></script>
```

This plugin ignores diacritical marks when performing a full text search (e.g., "cafe" will also match "café").

## Google Analytics

> Google's Universal Analytics service will no longer process new data in standard properties beginning July 1, 2023. Prepare now by setting up and switching over to a Google Analytics 4 property and docsify's gtag.js plugin.

Install the plugin and configure the track id.

```html
<script>
  window.$docsify = {
    ga: 'UA-XXXXX-Y',
  };
</script>
<script src="//cdn.jsdelivr.net/npm/docsify@5/dist/docsify.min.js"></script>
<script src="//cdn.jsdelivr.net/npm/docsify@5/dist/plugins/ga.min.js"></script>
```

Configure by `data-ga`.

<!-- prettier-ignore -->
```html
<script src="//cdn.jsdelivr.net/npm/docsify@5/dist/docsify.min.js" data-ga="UA-XXXXX-Y"></script>
<script src="//cdn.jsdelivr.net/npm/docsify@5/dist/plugins/ga.min.js"></script>
```

## Google Analytics 4 (GA4)

Install the plugin and configure the track id.

```html
<script>
  // Single ID
  window.$docsify = {
    gtag: 'UA-XXXXX-Y',
  };

  // Multiple IDs
  window.$docsify = {
    gtag: [
      'G-XXXXXXXX', // Google Analytics 4 (GA4)
      'UA-XXXXXXXX', // Google Universal Analytics (GA3)
      'AW-XXXXXXXX', // Google Ads
      'DC-XXXXXXXX', // Floodlight
    ],
  };
</script>
<script src="//cdn.jsdelivr.net/npm/docsify@5/dist/docsify.min.js"></script>
<script src="//cdn.jsdelivr.net/npm/docsify@5/dist/plugins/gtag.min.js"></script>
```

## Emoji

Renders a larger collection of emoji shorthand codes. Without this plugin, Docsify is able to render only a limited number of emoji shorthand codes.

!> Deprecated as of v4.13. Docsify no longer requires this plugin for full emoji support.

```html
<script src="//cdn.jsdelivr.net/npm/docsify@5/dist/plugins/emoji.min.js"></script>
```

## External Script

If the script on the page is an external one (imports a js file via `src` attribute), you'll need this plugin to make it work.

```html
<script src="//cdn.jsdelivr.net/npm/docsify@5/dist/plugins/external-script.min.js"></script>
```

## Zoom image

Medium's image zoom. Based on [medium-zoom](https://github.com/francoischalifour/medium-zoom).

```html
<script src="//cdn.jsdelivr.net/npm/docsify@5/dist/plugins/zoom-image.min.js"></script>
```

Exclude the special image

```markdown
![](image.png ':no-zoom')
```

## Edit on github

Add `Edit on github` button on every pages. Provided by [@njleonzhang](https://github.com/njleonzhang), see this [document](https://github.com/njleonzhang/docsify-edit-on-github)

## Demo code with instant preview and jsfiddle integration

With this plugin, sample code can be rendered on the page instantly, so that the readers can see the preview immediately.
When readers expand the demo box, the source code and description are shown there. if they click the button `Try in Jsfiddle`,
`jsfiddle.net` will be open with the code of this sample, which allow readers to revise the code and try on their own.

[Vue](https://njleonzhang.github.io/docsify-demo-box-vue/) and [React](https://njleonzhang.github.io/docsify-demo-box-react/) are both supported.

## Copy to Clipboard

Add a simple `Click to copy` button to all preformatted code blocks to effortlessly allow users to copy example code from your docs. Provided by [@jperasmus](https://github.com/jperasmus)

```html
<script src="//cdn.jsdelivr.net/npm/docsify-copy-code/dist/docsify-copy-code.min.js"></script>
```

See [here](https://github.com/jperasmus/docsify-copy-code/blob/master/README.md) for more details.

## Disqus

Disqus comments. https://disqus.com/

```html
<script>
  window.$docsify = {
    disqus: 'shortname',
  };
</script>
<script src="//cdn.jsdelivr.net/npm/docsify@5/dist/plugins/disqus.min.js"></script>
```

## Gitalk

[Gitalk](https://github.com/gitalk/gitalk) is a modern comment component based on GitHub Issue and Preact.

```html
<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/gitalk/dist/gitalk.css" />

<script src="//cdn.jsdelivr.net/npm/docsify@5/dist/plugins/gitalk.min.js"></script>
<script src="//cdn.jsdelivr.net/npm/gitalk/dist/gitalk.min.js"></script>
<script>
  const gitalk = new Gitalk({
    clientID: 'GitHub Application Client ID',
    clientSecret: 'GitHub Application Client Secret',
    repo: 'GitHub repo',
    owner: 'GitHub repo owner',
    admin: [
      'GitHub repo collaborators, only these guys can initialize github issues',
    ],
    // facebook-like distraction free mode
    distractionFreeMode: false,
  });
</script>
```

## Pagination

Pagination for docsify. By [@imyelo](https://github.com/imyelo)

```html
<script src="//cdn.jsdelivr.net/npm/docsify@5/dist/docsify.min.js"></script>
<script src="//cdn.jsdelivr.net/npm/docsify-pagination/dist/docsify-pagination.min.js"></script>
```

Click [here](https://github.com/imyelo/docsify-pagination#readme) to get more information.

## Tabs

A docsify.js plugin for displaying tabbed content from markdown.

- [Documentation & Demos](https://jhildenbiddle.github.io/docsify-tabs)

Provided by [@jhildenbiddle](https://github.com/jhildenbiddle/docsify-tabs).

## More plugins

See [awesome-docsify](awesome?id=plugins)
