1. Называть переменные так, чтобы их имена раскрывали бы их сущность, их роль в программе. При таком подходе их удобно будет искать в коде, а тот, кто увидит этот код, легче сможет понять смысл выполняемых им действий.

Плохой пример:
let y = new Date().getFullYear();

Хороший пример:
let currentYear = new Date().getFullYear();

2. Использовать для функций длинные описательные имена. Учитывая то, что функция представляет собой описание выполнения некоего действия, её имя должно представлять собой глагол или фразу, полностью описывающую суть функции. Имена аргументов нужно подбирать так, чтобы они адекватно описывали бы представляемые ими данные. Имена функций должны сообщать читателю кода о том, что именно делают эти функции.

Плохой пример:
function time () {
...
}

Хороший пример:
function showTime () {
...
}

3. Писать хорошую документацию к своему коду — тогда тот, кто столкнётся с ним в будущем, поймёт, что и почему в этом коде делается. 

Плохой пример:
function areaOfCircle (radius) {
  return 3.14 * radius ** 2
}

Хороший пример:
const PI = 3.14 // Число Пи, округлённое до двух знаков после запятой

function areaOfCircle (radius) {
  // Функция реализует математическую формулу вычисления площади круга:
  // Число Пи умножается на квадрат радиуса круга
  return PI * radius ** 2
}

4. Избегать испльзования console.log. Команда console.log представляет собой простой, быстрый и удобный инструмент для отладки программ. Существуют, конечно, и более продвинутые средства такого рода, но я думаю, что console.log всё ещё пользуются практически все программисты. Если, используя console.log для отладки, не убирать вовремя вызовы этой команды, ставшие ненужными, консоль скоро придёт в полный беспорядок. При этом надо отметить, что некоторые команды логирования имеет смысл оставлять даже в коде проектов, полностью готовых к работе. Например — команды, выводящие сообщения об ошибках и предупреждения.

5. Точки с запятой должны присутствовать после каждого выражения, даже если их, казалось бы, можно пропустить.
Есть языки, в которых точка с запятой необязательна и редко используется. Однако в JavaScript бывают случаи, когда перенос строки не интерпретируется, как точка с запятой, что может привести к ошибкам. 

Плохой пример:
let number = 34
let circle = 23

Хороший пример:

let number = 34;
let circle = 23;

6. Использовать автоматизированные средства проверки, так называемые «линтеры» – это инструменты, которые могут автоматически проверять стиль кода и вносить предложения по его улучшению.
Самое замечательное в них то, что проверка стиля может также найти программные ошибки, такие как опечатки в именах переменных или функций. Из-за этой особенности использовать линтер рекомендуется, даже если вы не хотите придерживаться какого-то конкретного «стиля кода».

7.Ограничивать число строк в файлах и максимального уровня вложенности кода.

Плохой пример:
for (let i = 0; i < 10; i++) {
  if (cond) {
    ... // <- ещё один уровень вложенности
  }
}


Хороший пример:
for (let i = 0; i < 10; i++) {
  if (!cond) continue;
  ...  // <- нет лишнего уровня вложенности
}

8. Писать короткие функции, решающие одну задачу. Функции легче поддерживать, они становятся гораздо более понятными, читабельными, если они направлены на решение лишь какой-то одной задачи. Если мы сталкиваемся с ошибкой, то, при использовании маленьких функций, найти источник этой ошибки становится гораздо легче. Кроме того, улучшаются возможности по повторному использованию кода.


Плохой пример:
function sumAndAverageArray(array) {
  let sum = array.reduce((number, currentSum) => number + currentSum)
  return sum / array.length
}

Хороший пример:
function sumArray(array) {
  return array.reduce((number, currentSum) => number + currentSum)
}

function averageArray(array) {
  return sumArray(array) / array.length
}

9. Использовать отступы.
Горизонтальные отступы: два или четыре пробела.

Плохой пример:
function areaOfCircle (radius) {
return 3.14 * radius ** 2
}

Хороший пример:
function areaOfCircle (radius) {
  return 3.14 * radius ** 2
}


Вертикальные отступы: пустые строки для разбивки кода на «логические блоки».
Даже одну функцию часто можно разделить на логические блоки. В примере ниже разделены инициализация переменных, основной цикл и возвращаемый результат:


Плохой пример:
function pow(x, n) {
  let result = 1;
  for (let i = 0; i < n; i++) {
  result *= x;
  }
  return result;
}

Хороший пример:
function pow(x, n) {
  let result = 1;
                
  for (let i = 0; i < n; i++) {
    result *= x;
  }
               
  return result;
}

10. Не использовать для названия переменных русские слова в транслите на английский.

Плохой пример:
let nomer = 23;

Хороший пример:
let number = 23;