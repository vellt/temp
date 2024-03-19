```c#
/*
 Kiválasztás tétele:
eldöntés tétele annyival kiegészítve, hogy amennyiben van/talált olyan elemet, ami a feltételnek megfelel akkor megadja az indexét
 */

// 10 egész számot generáljon [-50, 50]-ban
// mondja meg, hogy van e benne pozitív szám
// amennyiben igen mondja meg annak az indexét
Random r = new Random();
int[] egeszSzamok = new int[10];
for (int i = 0; i < egeszSzamok.Length; i++)
{
	egeszSzamok[i] = r.Next(101)-50;
}

int index = -1;
for (int i = 0; index==-1 && i < egeszSzamok.Length; i++)
{
	if(egeszSzamok[i]>=0)
	{
		index = i;
	}
}
if (index != -1)
{
	Console.WriteLine("találtam pozitív számot");
	Console.WriteLine(egeszSzamok[index]);
}
else
{
	Console.WriteLine("nincs benne pozitív szám");
}

// max/min kiválasztás
// rendezetlen elemek (szám, karakter, szöveg) közül kiválasztjuk a legnagyobbat vagy a legkisebbet. 
int maxIndex = 0;
for (int i = 1; i < egeszSzamok.Length; i++)
{
	if (egeszSzamok[maxIndex] < egeszSzamok[i])
	{
		maxIndex = i;
	}
}
```