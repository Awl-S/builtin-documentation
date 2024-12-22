# Документация по встроенным функциям GCC/Clang

## Введение
Компиляторы GCC и Clang предоставляют набор встроенных функций (`__builtin_*`), которые позволяют программистам напрямую использовать низкоуровневые операции, оптимизировать код и обращаться к специфическим возможностям процессора. Эти функции часто сопоставляются с аппаратными инструкциями или реализуются компилятором в эффективной форме.

---

## 1. Функции для работы с битами
Эти функции выполняют операции на уровне битового представления чисел.

### `__builtin_popcount`
- **Описание**: Подсчитывает количество установленных битов (1) в двоичном представлении числа типа `unsigned int`.
- **Параметры**:
  - `unsigned int x`: Входное число.
- **Возвращаемое значение**: Количество единиц в двоичном представлении `x`.

### `__builtin_popcountl`
- **Описание**: Подсчитывает количество установленных битов в числе типа `unsigned long`.
- **Параметры**:
  - `unsigned long x`: Входное число.
- **Возвращаемое значение**: Количество единиц в двоичном представлении `x`.

### `__builtin_popcountll`
- **Описание**: Подсчитывает количество установленных битов в числе типа `unsigned long long`.
- **Параметры**:
  - `unsigned long long x`: Входное число.
- **Возвращаемое значение**: Количество единиц в двоичном представлении `x`.

### `__builtin_ctz`
- **Описание**: Подсчитывает количество завершающих нулей в числе типа `unsigned int`.
- **Параметры**:
  - `unsigned int x`: Входное число.
- **Возвращаемое значение**: Количество завершающих нулей в двоичном представлении `x`. Возвращает неопределённое значение, если `x` равно 0.

### `__builtin_ctzl`
- **Описание**: Подсчитывает количество завершающих нулей в числе типа `unsigned long`.
- **Параметры**:
  - `unsigned long x`: Входное число.
- **Возвращаемое значение**: Количество завершающих нулей в двоичном представлении `x`. Возвращает неопределённое значение, если `x` равно 0.

### `__builtin_ctzll`
- **Описание**: Подсчитывает количество завершающих нулей в числе типа `unsigned long long`.
- **Параметры**:
  - `unsigned long long x`: Входное число.
- **Возвращаемое значение**: Количество завершающих нулей в двоичном представлении `x`. Возвращает неопределённое значение, если `x` равно 0.

### `__builtin_clz`
- **Описание**: Подсчитывает количество ведущих нулей в числе типа `unsigned int`.
- **Параметры**:
  - `unsigned int x`: Входное число.
- **Возвращаемое значение**: Количество ведущих нулей в двоичном представлении `x`. Возвращает неопределённое значение, если `x` равно 0.

### `__builtin_clzl`
- **Описание**: Подсчитывает количество ведущих нулей в числе типа `unsigned long`.
- **Параметры**:
  - `unsigned long x`: Входное число.
- **Возвращаемое значение**: Количество ведущих нулей в двоичном представлении `x`. Возвращает неопределённое значение, если `x` равно 0.

### `__builtin_clzll`
- **Описание**: Подсчитывает количество ведущих нулей в числе типа `unsigned long long`.
- **Параметры**:
  - `unsigned long long x`: Входное число.
- **Возвращаемое значение**: Количество ведущих нулей в двоичном представлении `x`. Возвращает неопределённое значение, если `x` равно 0.

### `__builtin_parity`
- **Описание**: Возвращает чётность количества единиц в числе типа `unsigned int`. Возвращает 1, если количество единиц нечётное, иначе 0.
- **Параметры**:
  - `unsigned int x`: Входное число.
- **Возвращаемое значение**: `1`, если количество единиц нечётное, `0` в противном случае.

### `__builtin_parityl`
- **Описание**: Возвращает чётность количества единиц в числе типа `unsigned long`.
- **Параметры**:
  - `unsigned long x`: Входное число.
- **Возвращаемое значение**: `1`, если количество единиц нечётное, `0` в противном случае.

### `__builtin_parityll`
- **Описание**: Возвращает чётность количества единиц в числе типа `unsigned long long`.
- **Параметры**:
  - `unsigned long long x`: Входное число.
- **Возвращаемое значение**: `1`, если количество единиц нечётное, `0` в противном случае.

---

## 2. Функции проверки переполнения
Эти функции проверяют условия переполнения при арифметических операциях.

### `__builtin_add_overflow`
- **Описание**: Выполняет сложение и проверяет наличие переполнения.
- **Параметры**:
  - `T x`: Первый операнд.
  - `T y`: Второй операнд.
  - `T* result`: Указатель для сохранения результата.
- **Возвращаемое значение**: Возвращает `1`, если произошло переполнение, иначе `0`.

### `__builtin_sub_overflow`
- **Описание**: Выполняет вычитание и проверяет наличие переполнения.
- **Параметры**:
  - `T x`: Первый операнд.
  - `T y`: Второй операнд.
  - `T* result`: Указатель для сохранения результата.
- **Возвращаемое значение**: Возвращает `1`, если произошло переполнение, иначе `0`.

### `__builtin_mul_overflow`
- **Описание**: Выполняет умножение и проверяет наличие переполнения.
- **Параметры**:
  - `T x`: Первый операнд.
  - `T y`: Второй операнд.
  - `T* result`: Указатель для сохранения результата.
- **Возвращаемое значение**: Возвращает `1`, если произошло переполнение, иначе `0`.

---

## 3. Функции для работы с памятью
Эти функции предоставляют эффективные способы работы с блоками памяти.

### `__builtin_memcpy`
- **Описание**: Копирует блок памяти из источника в назначение.
- **Параметры**:
  - `void* dest`: Указатель на место назначения.
  - `const void* src`: Указатель на источник.
  - `size_t n`: Количество байтов для копирования.
- **Возвращаемое значение**: Указатель на место назначения (`dest`).

### `__builtin_memset`
- **Описание**: Заполняет блок памяти указанным значением.
- **Параметры**:
  - `void* dest`: Указатель на блок памяти для заполнения.
  - `int c`: Значение для заполнения.
  - `size_t n`: Количество байтов для заполнения.
- **Возвращаемое значение**: Указатель на место назначения (`dest`).

### `__builtin_memmove`
- **Описание**: Перемещает блок памяти из источника в назначение. Безопасно работает с перекрывающимися областями памяти.
- **Параметры**:
  - `void* dest`: Указатель на место назначения.
  - `const void* src`: Указатель на источник.
  - `size_t n`: Количество байтов для перемещения.
- **Возвращаемое значение**: Указатель на место назначения (`dest`).

---

## 4. Оптимизация управления потоком
Эти функции предоставляют подсказки компилятору для оптимизации потока выполнения.

### `__builtin_expect`
- **Описание**: Предоставляет компилятору информацию о вероятности выполнения условия.
- **Параметры**:
  - `long exp`: Выражение для оценки.
  - `long c`: Ожидаемое значение выражения.
- **Возвращаемое значение**: Возвращает значение `exp`. Компилятор оптимизирует код, исходя из предположения, что `exp == c`.

---

## 5. Проверка типов и констант
Эти функции помогают в проверке типов и оценке констант.

### `__builtin_types_compatible_p`
- **Описание**: Проверяет, совместимы ли два типа.
- **Параметры**:
  - `T1`: Первый тип.
  - `T2`: Второй тип.
- **Возвращаемое значение**: Возвращает `1`, если типы совместимы, иначе `0`.

### `__builtin_constant_p`
- **Описание**: Проверяет, является ли значение константой времени компиляции.
- **Параметры**:
  - `exp`: Выражение для проверки.
- **Возвращаемое значение**: Возвращает `1`, если выражение является константой времени компиляции, иначе `0`.

---

## 6. Математические и утилитные функции
Эти функции предоставляют базовые математические и вспомогательные операции.

### `__builtin_abs`
- **Описание**: Возвращает абсолютное значение целого числа.
- **Параметры**:
  - `int x`: Входное число.
- **Возвращаемое значение**: Абсолютное значение `x`.

### `__builtin_labs`
- **Описание**: Возвращает абсолютное значение числа типа `long`.
- **Параметры**:
  - `long x`: Входное число.
- **Возвращаемое значение**: Абсолютное значение `x`.

### `__builtin_llabs`
- **Описание**: Возвращает абсолютное значение числа типа `long long`.
- **Параметры**:
  - `long long x`: Входное число.
- **Возвращаемое значение**: Абсолютное значение `x`.

---

## Примечания
1. Эти встроенные функции специфичны для платформы и оптимизируются компилятором.
2. Некоторые функции, такие как `__builtin_expect`, могут не давать прироста производительности во время выполнения, но помогают в оптимизации кода на этапе компиляции.
3. Функции, такие как `__builtin_popcount`, могут использовать аппаратные инструкции (например, POPCNT), если они поддерживаются процессором.