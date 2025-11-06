# Максим Байдаков

## Обо мне
Привет! Я студент первого курса ИРИТ-РТФ. Обучаюсь на направлении "Прикладная информатика".

## Мои интересы
- Программирование на Python 🐍  
- Обучение C# 💻  
- Просмотр фильмов 🎬  
- Бег 🏃‍♂️

## Мои навыки
1. Знаю основы Python  
2. Могу написать телеграм-бота 🤖  
3. Владею базовым английским  
4. Могу работать с нейросетями 🧠

## Расписание на неделю

| День недели | Занятие           | Время  |
|-------------|-------------------|--------|
| Понедельник | Иностранный язык  | 10:00  |
| Вторник     | Физкультура       | 12:00  |
| Среда       | Свободный день    |   —    |
| Четверг     | ИТИС              | 17:45  |
| Пятница     | Математика        | 12:00  |

## Python-код для решения квадратных уравнений

```Python
import math
import cmath

def solve_quadratic(a, b, c):
    if a == 0:
        if b == 0:
            if c == 0:
                return "Бесконечно много решений (0 = 0)."
            else:
                return "Нет решений (противоречие: {} = 0).".format(c)
        else:
            x = -c / b
            return f"Линейное уравнение. Корень: x = {x}"
    
    D = b**2 - 4*a*c

    if D > 0:
        x1 = (-b + math.sqrt(D)) / (2*a)
        x2 = (-b - math.sqrt(D)) / (2*a)
        return f"Два вещественных корня: x1 = {x1}, x2 = {x2}"
    elif D == 0:
        x = -b / (2*a)
        return f"Один вещественный корень: x = {x}"
    else:
        sqrt_D = cmath.sqrt(D)
        x1 = (-b + sqrt_D) / (2*a)
        x2 = (-b - sqrt_D) / (2*a)
        return f"Два комплексных корня: x1 = {x1}, x2 = {x2}"

if __name__ == "__main__":
    print("Решение квадратного уравнения ax² + bx + c = 0")
    try:
        a = float(input("Введите коэффициент a: "))
        b = float(input("Введите коэффициент b: "))
        c = float(input("Введите коэффициент c: "))
        result = solve_quadratic(a, b, c)
        print(result)
    except ValueError:
        print("Ошибка: введите числовые значения коэффициентов.")
```
## C# код для решения квадратных уравнений
```C#
using System;

class QuadraticEquationSolver
{
    static void Main()
    {
        Console.WriteLine("Решение квадратного уравнения ax^2 + bx + c = 0");
        Console.Write("Введите коэффициент a: ");
        if (!double.TryParse(Console.ReadLine(), out double a))
        {
            Console.WriteLine("Некорректное значение для a.");
            return;
        }

        Console.Write("Введите коэффициент b: ");
        if (!double.TryParse(Console.ReadLine(), out double b))
        {
            Console.WriteLine("Некорректное значение для b.");
            return;
        }

        Console.Write("Введите коэффициент c: ");
        if (!double.TryParse(Console.ReadLine(), out double c))
        {
            Console.WriteLine("Некорректное значение для c.");
            return;
        }

        SolveQuadratic(a, b, c);
    }

    static void SolveQuadratic(double a, double b, double c)
    {
        const double epsilon = 1e-10; // для сравнения с нулём с учётом погрешности

        if (Math.Abs(a) < epsilon)
        {
            // Уравнение вырождается в линейное: bx + c = 0
            if (Math.Abs(b) < epsilon)
            {
                if (Math.Abs(c) < epsilon)
                {
                    Console.WriteLine("Уравнение имеет бесконечно много решений.");
                }
                else
                {
                    Console.WriteLine("Уравнение не имеет решений.");
                }
            }
            else
            {
                double x = -c / b;
                Console.WriteLine($"Уравнение линейное. Корень: x = {x:F6}");
            }
            return;
        }

        double discriminant = b * b - 4 * a * c;

        if (discriminant > epsilon)
        {
            double sqrtD = Math.Sqrt(discriminant);
            double x1 = (-b + sqrtD) / (2 * a);
            double x2 = (-b - sqrtD) / (2 * a);
            Console.WriteLine("Два вещественных корня:");
            Console.WriteLine($"x1 = {x1:F6}");
            Console.WriteLine($"x2 = {x2:F6}");
        }
        else if (Math.Abs(discriminant) <= epsilon)
        {
            double x = -b / (2 * a);
            Console.WriteLine($"Один вещественный корень (кратный): x = {x:F6}");
        }
        else
        {
            double realPart = -b / (2 * a);
            double imagPart = Math.Sqrt(-discriminant) / (2 * a);
            Console.WriteLine("Два комплексных корня:");
            Console.WriteLine($"x1 = {realPart:F6} + {imagPart:F6}i");
            Console.WriteLine($"x2 = {realPart:F6} - {imagPart:F6}i");
        }
    }
}
```
## Pascal код для приветствия мира
```Pascal
program HelloWorld;

begin
  writeln('Hello World');
end.
```
