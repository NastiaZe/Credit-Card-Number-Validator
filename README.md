# Отчёт о тестировании приложения по валидации номера банковской карты.
### Краткое описание

19.12.2020 было проведено функциональное тестирование по валидации номеров банковских карт.

Всего  затрачено времени : 2 часа

##В результате тестирования выявлены следующие дефекты:

[Дефект №1](https://github.com/NastiaZe/Credit-Card-Number-Validator/issues/1)
  [Дефект №2](https://github.com/NastiaZe/Credit-Card-Number-Validator/issues/2)

[Дефект №3](https://github.com/NastiaZe/Credit-Card-Number-Validator/issues/3)

## Описание процесса тестирования

В процессе тестирования использовались следующие артефакты:

1.  [Руководство по установке IntelliJ IDEA](https://github.com/netology-code/javaqa-homeworks/blob/master/intro/idea.md)
2.  наработки кода от программиста 
public class Main {
  public static void main(String[] args) {
    // TODO: подставлять номер карты нужно сюда между двойными кавычками, без пробелов
    String number = "5351719427810741";
    System.out.println(String.format("Result is %s", isValidCardNumber(number) ? "OK" : "FAIL"));
  }

  public static boolean isValidCardNumber(String number) {
    if (number == null) {
      return false;
    }

    if (number.length() != 16) {
      return false;
    }

    long result = 0;
    for (int i = 0; i < number.length(); i++) {
      int digit;
      try {
        digit = Integer.parseInt(number.charAt(i) + "");
      } catch (NumberFormatException e) {
        return false;
      }

      if (i % 2 == 0) {
        digit *= 2;
        if (digit > 9) {
          digit -= 9;
        }
      }
      result += digit;
    }

    return (result != 0) && (result % 10 == 0);
  }
3. [Сайт] (https://www.getcreditcardnumbers.com/generated-credit-card-numbers)

В качестве тестовых данных использовались данные:номера кредитных карт:
5242581325387609
4539104901430753
4532446052135815
6011529666624897
4640085768835455
4716752712377459
379788889484633
375704947327593
38707151192958

## Ожидаемые данные:

валидные карты для проверки - ответ приложения Result is OK
не валидные карты  для проверки  - ответ приложения Result is FAIL

## Тестирование производилось в следующем окружении:

Micrsoft Windows 10 pro, версия: 1909 сборка 18363.418  
openjdk version "11.0.9.1" 2020.11.04
