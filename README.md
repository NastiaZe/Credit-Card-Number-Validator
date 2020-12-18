# ����� � ������������ ���������� �� ��������� ������ ���������� �����.
### ������� ��������

19.12.2020 ���� ��������� �������������� ������������ �� ��������� ������� ���������� ����.

�����  ��������� ������� : 2 ����

##� ���������� ������������ �������� ��������� �������:

[������ �1](https://github.com/NastiaZe/Credit-Card-Number-Validator/issues/1)
  [������ �2](https://github.com/NastiaZe/Credit-Card-Number-Validator/issues/2)

[������ �3](https://github.com/NastiaZe/Credit-Card-Number-Validator/issues/3)

## �������� �������� ������������

� �������� ������������ �������������� ��������� ���������:

1.  [����������� �� ��������� IntelliJ IDEA](https://github.com/netology-code/javaqa-homeworks/blob/master/intro/idea.md)
2.  ��������� ���� �� ������������ 
public class Main {
  public static void main(String[] args) {
    // TODO: ����������� ����� ����� ����� ���� ����� �������� ���������, ��� ��������
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
3. [����] (https://www.getcreditcardnumbers.com/generated-credit-card-numbers)

� �������� �������� ������ �������������� ������:������ ��������� ����:
5242581325387609
4539104901430753
4532446052135815
6011529666624897
4640085768835455
4716752712377459
379788889484633
375704947327593
38707151192958

## ��������� ������:

�������� ����� ��� �������� - ����� ���������� Result is OK
�� �������� �����  ��� ��������  - ����� ���������� Result is FAIL

## ������������ ������������� � ��������� ���������:

Micrsoft Windows 10 pro, ������: 1909 ������ 18363.418  
openjdk version "11.0.9.1" 2020.11.04
