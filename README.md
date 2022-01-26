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

You can override the default config in your `mysite.yml`:

```
ViteHelper\Vite\ViteHelper:
  forceProductionMode: false
  devHostNeedle: '.test'
  devPort: 3000
  jsSrcDirectory: 'public_src/'
  mainJS: 'main.js'
  manifestDir: '/public/manifest.json'
```

E.g., if you use TypeScript, change the `mainJs` prop to `"main.ts"`. If you set `forceProductionMode` to true, only build files will be served - which will happen on your live site anyway. 
Set the `devHostNeedle` to distinguish your live site from your local environment. 

The config must match the `vite.config.js`. You need to **?flush** after making changes to yml configs. 

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

