[user]: mahankals
[repo]: CakePHP-Vite-Plugin

[title]: [repo]
[name]: package-teplate

# CakePHP-Vite-Plugin

[![Latest Version](https://img.shields.io/github/v/tag/mahankals/CakePHP-Vite-Plugin?label=Latest)](https://github.com/mahankals/CakePHP-Vite-Plugin)
[![Stable Version](https://img.shields.io/github/v/release/mahankals/CakePHP-Vite-Plugin?label=Stable&sort=semver)](https://github.com/mahankals/CakePHP-Vite-Plugin/releases)
[![License: MIT](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![Total Downloads](https://img.shields.io/github/downloads/mahankals/CakePHP-Vite-Plugin/total.svg)](https://github.com/mahankals/CakePHP-Vite-Plugin/releases)

[![GitHub Stars](https://img.shields.io/github/stars/mahankals/CakePHP-Vite-Plugin?style=social)](https://github.com/mahankals/CakePHP-Vite-Plugin/stargazers)
[![GitHub Forks](https://img.shields.io/github/forks/mahankals/CakePHP-Vite-Plugin?style=social)](https://github.com/mahankals/CakePHP-Vite-Plugin/network/members)
[![GitHub Watchers](https://img.shields.io/github/watchers/mahankals/CakePHP-Vite-Plugin?style=social)](https://github.com/mahankals/CakePHP-Vite-Plugin/watchers)

<!-- [![Latest Stable Version](https://poser.pugx.org/mahankals/CakePHP-Vite-Plugin/v/stable)](https://packagist.org/packages/mahankals/CakePHP-Vite-Plugin)
[![Total Downloads](https://poser.pugx.org/mahankals/CakePHP-Vite-Plugin/downloads)](https://packagist.org/packages/mahankals/CakePHP-Vite-Plugin)
 -->

Package description

---

## Features

- Easy Mapping of assets (build / resourced) with application
- Live Reload
- DDEV supports

## Installation

You can install this plugin directly from GitHub using Composer:

1. Add the GitHub repository to your app's `composer.json`:

   ```json
   {
     ...
     "repositories": [
         {
             "type": "vcs",
             "url": "https://github.com/mahankals/CakePHP-Vite-Plugin"
         }
     ],
     ...
   }
   ```

2. Add the plugin via Composer:

   ```bash
   composer require --dev mahankals/cakephp-vite-plugin
   ```

   **Note:** Append `:dev-main` at end for non-release version.

3. Load the plugin

   **Method 1: from terminal**

   ```bash
   bin/cake plugin load CakePhpViteHelper
   ```

   **Method 2: load in `Application.php`, bootstrap method**

   ```bash
   $this->addPlugin('CakePhpViteHelper');
   ```

4. Install Node packages with Vite Configuration

   **Method 1: Run with default (npm):**

   ```bash
   bin/cake vite-helper install
   ```

   **Method 2: specify package manager:**

   ```bash
   bin/cake vite-helper install --pm=pnpm
   ```

## Create Resource (example)

Create `resources/js/app.js`

```js
console.log("Welcome to CakePHP! 🎉");
```

Create `resources/css/app.css`

```css
body {
  background-color: skyblue !important;
}
```

## Use Helper

Either in `templates/layout/default.php` or `templates/**/*.php`

```php
<?= $this->Vite->asset(['resources/js/app.js','resources/css/app.css']) ?>
```

## Bundle Assest

**Method 1: Use Vite dev server with live reload:**

```bash
npm run dev
```

**Method 2: for production:**

```bash
npm run build
```

## Extra

### To get url of resource

```php
<?= $this->Vite->url('resources/img/cake.logo.svg') ?>
```

Result:

1. with `npm run dev'

   ```html
   https://localhost:5173/resources/img/cake.logo.svg
   ```

2. with `npm run dev'

   ```html
   https:///build/assets/cake.logo-1vCAGwyb.svg
   ```

### Using ddev?

Just update `.ddev/config.yaml` by adding

```yaml
web_extra_exposed_ports:
  - name: vite
    container_port: 5173
    http_port: 5172
    https_port: 5173
```

## Contributing

Contributions, issues, and feature requests are welcome!

## Author

Atul Mahankal – [atulmahankal@gmail.com](mailto:atulmahankal@gmail.com)

## License

This library is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).
