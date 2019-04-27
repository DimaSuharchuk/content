---
id: standards-php
title: Стандарты кодирования PHP
category-area: Стандарты кодирования
category-order: 1
category-title: PHP
---

Стандарты кодирования PHP — самый главный набор требований и правил, который должны соблюдать разработчики, когда пишут код для Drupal, так как PHP является основным языком системы.

## Отступы и пробелы

Для отступов используйте 2 пробела. Табы запрещены.

Файлы должны быть отформатированы в Unix формате. Это значит, что переход на новую строку должен быть `\n`, а не `\r\n`.

Все файлы с кодом и текстом должны заканчиваться пустой строкой. Это решает проблемы с "\ No newline at end of file" и позволяет легче читать патчи.

Все блоки в начале PHP файла должны быть разделены пустой линией, это также касается `/** @file */` блока, объявления неймеспейсов, использование `use` и весь последующий код.

Примеры правильного форматирования:

```php
<?php

namespace This\Is\The\Namespace;

use Drupal\foo\Bar;

/**
 * Provides examples.
 */
class ExampleClassName {
```

```php
<?php

/**
 * @file
 * Provides example functionality.
 */

use Drupal\foo\Bar;

/**
 * Implements hook_help().
 */
function example_help($route_name) {
```

## Операторы

Все двоичные операторы (которые идут между двумя значениями), такие как `+`, `-`, `=`, `!=`, `==`, `>`, и т.д., должны иметь пробел перед и после оператора, для читаемости. Например, присвоение переменной должно выглядеть как `$foo = $bar;`, а не `$foo=$bar;`.

Для одинарных операторов (которые управляют только одним значением), таких как `++`, пробелы не ставятся, как до, так и после.

Для сравнения преобразованных типов мы используем `!=`, использование `<>` запрещено.


## Преобразование типа переменной

При преобразовании типа переменной ставится пробел между типом и самой переменной. Например `(int) $foo`.

## Управляющие конструкции

Управляющие конструкции включают в себя `if`, `for`, `while`, `switch` и т.д.

Пример `if` условия со всеми возможными  вариантами:

```php
if (condition1 || condition2) {
  action1;
}
elseif (condition3 && condition4) {
  action2;
}
else {
  defaultaction;
}
```

Не используйте `else if`, всегда должно быть `elseif`.

Управляющие конструкции должны иметь пробел между ключевым словом конструкции и открывающей скобкой, чтобы их было визуально проще отличать от вызова функий.

Всегда используйте фигурные скобки, даже тогда, когда их использование технически опционально. Они повышают читаемость кода и уменьшают вероятность логических ошибок при добавлении новых линий. Открывающая фигурная скобка всегда должна находиться на той же линии где и оператор, с пробелом перед ней. Закрывающая фигурная скобка всегда должна быть на собственной линии, и иметь тот же отступ как и открывающий оператор.

Пример `switch`:

```php
switch (condition) {
  case 1:
    action1;
    break;

  case 2:
    action2;
    break;

  default:
    defaultaction;
}
```

Пример `do-while`:

```php
do {
  actions;
} while ($condition);
```

