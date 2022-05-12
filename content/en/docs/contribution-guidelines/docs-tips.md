---
title: Documentation Tips & Tricks
---

In addition to the [full documentation](/docs/contribution-guidelines/#useful-resources), here are some commonly used functions in the Open Y Docs.

## General Styles

The old documentation made heavy use of horizontal rules `---` and slashes in headings `## // Heading`. We try to use standard Markdown headings for organization and remove those visual indicators for better accessibility.

Headings with a page should start with level 2 `##` in order to properly build the in-page navigation.

## Links

Internal links should be made with Markdown and page-relative locations, like:

```markdown
[Blocks](../user-documentation/blocks)
```

[Blocks](../user-documentation/blocks)

## Video Embeds

Videos can be embedded using [Hugo's youtube or vimeo shortcodes](https://gohugo.io/content-management/shortcodes/#youtube). These take the form:

```go-html-template
{{</* youtube w7Ft2ymGmfc */>}}
{{</* vimeo 146022717 */>}}
```

To replace regular YouTube links with the shortcode you can use the following regex:

```go-html-template
find: https?:\/\/(?:www\.)?(?:youtube\.com|youtu\.be)\/(?:watch\?v=)?([\w-]+)
replacement: {{</* youtube w7Ft2ymGmfc */>}}
```

## Tips

The old community documentation used headings inside blockquotes (starting each line with `>`). That formatting doesn't work in Hugo. We can use [Docsy alerts](https://www.docsy.dev/docs/adding-content/shortcodes/#alert) instead.

```go-html-template
{{%/* alert title="Warning" */%}}
This is a warning.
{{%/* /alert */%}}
```

{{% alert title="Warning" %}}
This is a warning.
{{% /alert %}}