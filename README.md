# WP Post Subtitle

[![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)](https://github.com/tikhomirov/wp-postsubtitle-plugin/releases)
[![WordPress](https://img.shields.io/badge/WordPress-4.6%2B-blue.svg)](https://wordpress.org/)
[![PHP](https://img.shields.io/badge/PHP-7.0%2B-purple.svg)](https://php.net/)

Adds a subtitle field to posts and pages when enabled via theme support.

## Requirements

| Component | Minimum |
|-----------|---------|
| **WordPress** | 4.6 |
| **PHP** | 7.0 |

## Features

- Subtitle meta box in post editor
- Template helper functions
- Theme support gate: `add_theme_support('subtitle')`
- Composer package `rwsite/wp-postsubtitle-plugin`

## Installation

### Composer

```bash
composer require rwsite/wp-postsubtitle-plugin
```

### Manual

1. Download the [latest release](https://github.com/tikhomirov/wp-postsubtitle-plugin/releases).
2. Upload to `wp-content/plugins/wp-postsubtitle-plugin/`.
3. Activate **Post Subtitle**.

## Usage

In theme `functions.php`:

```php
add_theme_support('subtitle');
```

## License

GPL-2.0-or-later

## Author

Aleksey Tikhomirov — [rwsite.ru](https://rwsite.ru)

---

## Русский

Плагин добавляет подзаголовок к записям. Включение: `add_theme_support('subtitle');` в теме.
