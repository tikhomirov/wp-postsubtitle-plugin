# Проброс meta.subtitle в REST API

## Резюме задания

Нужно было открыть подзаголовок записи (`post meta` ключ `subtitle`) в WordPress REST API,
чтобы Гермес и `wp_client.py` могли читать и записывать его через
`GET/POST /wp-json/wp/v2/posts/{id}` (поле `meta.subtitle`).

Раньше значение сохранялось только из классической формы редактора и через
`update_post_meta`, в REST поле не регистрировалось.

## План действий

1. В `wp-postsubtitle-plugin.php` зарегистрировать мета-поле через `register_post_meta`.
2. Повторить проверку поддержки плагина: хук только если у темы есть
   `add_theme_support('subtitle')`.
3. Регистрировать для типа `post` (как форма редактора плагина) и для любых типов
   с `add_post_type_support('subtitle')`. Хук `init` с приоритетом 20, чтобы
   успеть после `after_setup_theme` и регистрации типов записей.
4. `sanitize_callback` — `sanitize_text_field`, как при сохранении из формы.
5. `auth_callback` — `current_user_can('edit_post', $object_id)`.
6. Проверка: `php -l wp-postsubtitle-plugin.php`.

## Что гоняли

- `php -l wp-postsubtitle-plugin.php` — синтаксических ошибок нет.

## Итоги / коммит

id коммита с правкой кода: `15698d7888c772582e2c3b6a2d7400536505853b`
(ветка `master`, сообщение: `feat: expose subtitle post meta in REST API`).
