# PHP Library Template

Template is a simple, yet powerful templating engine in single file.

![No Dependencies](https://img.shields.io/badge/no-dependencies-success.svg)

## Features ##

- Single file. No external dependencies
- No new "language" to learn. Familiar PHP syntax.
- Default templates extension .phtml

## Installation ##

Add the following to your composer file:

```json
    "require": {
        "sinevia/php-library-template": "1.*"
    },
```

## Functionality ##

### 1) From File ###

```php
\Sinevia\Template::fromFile($templateFilepath, $data = array());
```

### 2) From String ###

```php
\Sinevia\Template::fromString($templateString, $data = array());
```

### 3) Cache ###

```php
\Sinevia\Template::setCacheDirectory($cacheDirPath);
\Sinevia\Template::setCache($key, $content, $options = array());
\Sinevia\Template::getCache($key, $options = array());
```
### 3) Helpers ###

```php
\Sinevia\Template::minifyHtml($html);
\Sinevia\Template::minifyCss($css);
\Sinevia\Template::minifyJs($js);
```


## Usage ##

```php
$html = \Sinevia\Template::fromString($templateContent, [
     'page_meta_description' => $pageMetaDescription,
     'page_meta_keywords' => $pageMetaKeywords,
     'page_meta_robots' => $pageMetaRobots,
     'page_canonical_url' => $pageCanonicalUrl,
     'page_title' => $pageTitle,
     'page_content' => $pageContent,
]);
```

```php
\Sinevia\Template::setCache('key','content',array(
     'post'=>true,
     'get'=>true,
     'session'=>true,
     'expires'=>3600 // Default
));
```


## Layout ##

1. Template file:

```php
[layout::public/guest/layout.phtml]

CONTENT
```

2. Layout file:

```php
<?php echo $content; ?>

```
