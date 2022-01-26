# Silverstripe Vite Plugin

Installation:

```
composer require passchn/silverstripe-vite
```

In your `mysite.yml`:

```
Page:
extensions:
- ViteHelper\Vite\ViteDataExtension
```

Insert js / css tags in your template, e.g., `Page.ss`:

```
<head>
    ...
    $Vite.HeaderTags.RAW
</head>
<body>
    ...
    $Vite.BodyTags.RAW
</body>
```
Take a look at the [ViteHelper.php](https://github.com/passchn/silverstripe-vite/blob/master/src/Vite/ViteHelper.php) for more Information. 

* [Example vite.config.ts](https://github.com/passchn/silverstripe-vite/wiki/Example-vite.config.ts)

## Todo

* Make the plugin configurable 
