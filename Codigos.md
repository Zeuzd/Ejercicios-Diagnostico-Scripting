# Sorteo
``` c#
using System;
using System.Linq;

public class Sorteo
{
    public static void Main()
    {
        int numApostado = 1234;
        int numSorteado = 4231;
        int montoApostado = 1000;

        int premio = DeterminarPremio(numApostado, numSorteado, montoApostado);
        Console.WriteLine("Premio obtenido: " + premio);
    }
    public static int DeterminarPremio(int numApostado, int numSorteado, int montoApostado)
    {
        string sApostado = numApostado.ToString("D4");
        string sSorteado = numSorteado.ToString("D4");

        if (sApostado == sSorteado)
        {
            return montoApostado * 4500;
        }

        else if (sApostado.OrderBy(c => c).SequenceEqual(sSorteado.OrderBy(c => c)))
        {
            return montoApostado * 200;
        }

        else if (sApostado.Substring(1) == sSorteado.Substring(1))
        {
            return montoApostado * 400;
        }

        else if (sApostado.Substring(2) == sSorteado.Substring(2))
        {
            return montoApostado * 50;
        }

        else if (sApostado.Substring(3) == sSorteado.Substring(3))
        {
            return montoApostado * 5;
        }

        else
        {
            return 0;
        }
    }
}
```

# Fibonacci
``` c#
using System;

class Program
{
    static void Main()
    {
        imprimir(15);
    }

    static bool esPrimo(int num)
    {
        if (num < 2) return false;
        for (int i = 2; i * i <= num; i++)
        {
            if (num % i == 0) return false;
        }
        return true;
    }

    static void imprimir(int n)
    {
        int a = 0, b = 1, c;
        for (int i = 0; i < n; i++)
        {
            if (esPrimo(a)) Console.Write(a + " ");
            c = a + b;
            a = b;
            b = c;
        }
        Console.WriteLine();
    }
}
```

# Segundos a hora

``` c#
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine(segundosaHora(300));
    }


    static string segundosaHora(int seconds)
    {
        int hours = seconds / 3600;
        int minutes = (seconds % 3600) / 60;
        int sec = seconds % 60;
        return string.Format("{0:D2}:{1:D2}:{2:D2}", hours, minutes, sec);
    }
}
```

