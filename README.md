# Silverstripe Vite Plugin

## Installation

```
composer require passchn/silverstripe-vite
```

In your `mysite.yml`:

```
Page:
extensions:
- ViteHelper\Vite\ViteDataExtension
```

## Configuration

In your `mysite.yml`:

```
ViteHelper\Vite\ViteHelper:
  forceProductionMode: true
  devHostNeedle: '.test';
  devPort: 3000;
  jsSrcDirectory: 'public_src/';
  mainJS: 'main.js';
  manifestDir: '/public/manifest.json'
```

Take a look at the [ViteHelper.php](https://github.com/passchn/silverstripe-vite/blob/master/src/Vite/ViteHelper.php) for more Information. 

## Usage 

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

## Vite config

* [Example vite.config.ts](https://github.com/passchn/silverstripe-vite/wiki/Example-vite.config.ts)

