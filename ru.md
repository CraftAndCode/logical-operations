# Логические операторы

```package
core
radio
microphone
```

```template
basic.forever(function () {
	
})
```

```blocks
basic.forever(function () {
	
})
```
## Step 0 @showDialog
Привет! Сегодня мы научимся задавать Micro:bit более специфические условия для запуска программ.
## Step 1 @showDialog
### Логическое И
Иногда для выполнения действия требуется, чтобы выполнялось сразу несколько условий.
  
Например:  
- Если есть хлеб `И` колбаса, сделай бутерброд.
- Если домашняя работа сделана `И` ещё не ночь, играй в видеоигры.
  
Мы можем научить Micro:bit использовать ту же логику с помощью блока ``||logic.и||`` из вкладки  ``||logic.логика||``.
  
Например:
- Если кнопка `A` нажата `И` кнопка `B` нажата, воспроизведи звук.
```block
if (input.buttonIsPressed(Button.A) && input.buttonIsPressed(Button.B)) {
    soundExpression.giggle.playUntilDone()
})
```

## Step 2 @showDialog
### Логическое И
Мы можем использовать сразу несколько блоков ``||logic.и||`` чтобы добавить столько условий, сколько необходимо.
```blocks
if (input.buttonIsPressed(Button.A) && input.buttonIsPressed(Button.B) && input.logoIsPressed()) {
    basic.showIcon(IconNames.Yes)
    }
```
## Step 3 @showDialog
### Логическое И
Блок ``||logic.и||`` также полезен, если необходимо выполнить действие, когда несколько датчиков показывают определённые значения. Например, выполнить программу, если одновременно светло и жарко.
```block
if (input.temperature() > 30 && input.lightLevel() > 200) {
        basic.showString("It is warm and bright")
    }
```
## Step 4 @showHint
### Логическое И
Давай соберём программу с блоком ``||logic.и||``!
В этом примере Micro:bit показывает весёлый смайлик, если нажаты две кнопки одновременно. Загрузи этот пример в Micro:bit и проверь его работу самостоятельно!
```blocks
basic.forever(function () {
    if (input.buttonIsPressed(Button.A) && input.buttonIsPressed(Button.B)) {
        basic.showIcon(IconNames.Happy)
    } else {
        basic.clearScreen()
    }
})
```
## Step 5 @showDialog
### Логическое ИЛИ
Логическое ``||logic.или||`` используют,если действие нужно выполнить, если выполняется хотя ы одно из условий.
  
Например:
- Если в холодильнике нет молока `ИЛИ` масла, сходи в магазин.
- Если сегодня суббота `ИЛИ` воскресенье, не иди в школу.
  
- Если любая из кнопок нажата, воспроизведи звук.

```block
if (input.buttonIsPressed(Button.A) || input.buttonIsPressed(Button.B)) {
    soundExpression.giggle.playUntilDone()
})
```
## Step 6 @showHint
### Логическое ИЛИ
Замени в коде ``||logic.и||`` на ``||logic.или||``. Загрузи программу в Micro:bit. Что изменилось?
```blocks
basic.forever(function () {
    if (input.buttonIsPressed(Button.A) || input.buttonIsPressed(Button.B)) {
        basic.showIcon(IconNames.Happy)
    } else {
        basic.clearScreen()
    }
})
```
## Step 7 @showDialog
### Логическое НЕ
Человек легко понимает различие между двумя противоположными утверждениями.
  
Например:
- Светофор показывает зелёный свет и светофор показывает `НЕ` зелёный свет
- Домашнее задание выполнено и домашнее задание `НЕ` выполнено.
  
Чтобы сказать компьютеру выполнить действие при условии, противоположном другому условию, используется блок ``||logic.не||``.
  
Например:
- Если кнопка `НЕ` нажата, покажи сердечко, иначе не показывай ничего.
```block
 if (!(input.buttonIsPressed(Button.A))) {
        basic.showIcon(IconNames.Heart)
    } else {
        basic.clearScreen()
    }
```
## Step 8 @showHint
### Логическое НЕ
Используя всего три логических оператора, можно задать условие настолько сложное, насколько требуется. Например, в этой программе Micro:bit показывает солнце, если одновременно светло и ни одна из кнопок не нажата.
```blocks
basic.forever(function () {
    if (input.lightLevel() > 200 && !(input.buttonIsPressed(Button.A) || input.buttonIsPressed(Button.B))) {
        basic.showLeds(`
            # . # . #
            . # # # .
            # # # # #
            . # # # .
            # . # . #
            `)
    } else {
        basic.clearScreen()
    }
})
```

## Step 9
### Теперь твой черёд!
Вот задание для тебя! Напиши программу, которая делает следующее:
- Если кнопка `A` не нажата, покажи картинку, иначе не показывай ничего
- Если нажаты кнопка `A` и сенсор, покажи текст, иначе не показывай ничего
- Если темно или холодно, воспроизведи звук.

## Step 10 @showDialog
### Ответы:
Это один из вариантов программы. Твой код может выглядеть так же, но есть и другие варианты выполнения этого задания.
```blocks
basic.forever(function () {
    if (!(input.buttonIsPressed(Button.A))) {
        basic.showIcon(IconNames.Heart)
    } else {
        basic.clearScreen()
    }
    if (input.buttonIsPressed(Button.A) && input.logoIsPressed()) {
        basic.showString("Hello!")
    } else {
        basic.clearScreen()
    if (input.lightLevel() < 50 || input.temperature() < 10) {
        soundExpression.giggle.playUntilDone()
    }
})
```

## Step 11
Задание выполнено. Отлично! Теперь ты знаешь об операторах `И`, `ИЛИ` и `НЕ` и можешь использовать их в своих программах.