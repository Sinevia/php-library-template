# PHP Library Template

Template is a simple, yet powerful templating engine. Unlike other popular PHP templating engines, Template does not create its own "language", when PHP already does this.

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
