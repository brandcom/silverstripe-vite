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

*ViteHelper Config setting options:*
- If you set `forceProductionMode` to true, only build files will be served when running `npm run build` - which will happen on your live site anyway.
  - Setting this property to false will provide live updates when running `npm run dev` on a local environment.
- Set the `devHostNeedle` to distinguish your live site from your local environments domain extension.
- Set the `devPort` to an unused port (not the same port where the site is hosted from) for the Vite server to build asset from.
- Define the `mainJS` entry point to where your applications script file is located.
  - If you use TypeScript, change the `mainJs` prop to `"main.ts"`.
- Define the `manifestDir` for where the manifest file will be located.

## Usage

Insert JS / CSS tags in your main template, e.g., `Page.ss`:

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

The config must match the `vite.config.js`. You need to **?flush** after making changes to yml configs.

Take a look at the [ViteHelper.php](https://github.com/passchn/silverstripe-vite/blob/master/src/Vite/ViteHelper.php) for more Information. 

The config from your vite.config.js or vite.config.ts must match your ViteHelper config for this plugin.

See this [example vite.config.ts](https://github.com/brandcom/silverstripe-vite/wiki/example-vite-config) for default configuration. 

**Note:** When using vite below `2.9.0`, the server config will be different. [See this config](https://github.com/brandcom/silverstripe-vite/wiki/example-vite-config#vite-below-290).