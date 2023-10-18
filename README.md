```c#
Random random = new Random();
// [0,8]
int sz0 = random.Next(9);
//[20,80]
int sz1 = random.Next(61)+20;
// [5,100]
int sz2 = random.Next(96)+5;
// [100,200]
int sz3 = random.Next(101) + 100;
// [-100,50]
int sz4 = random.Next(151)-100;
// [-70,1]
int sz5 = random.Next(72)-70;
// [-100,-30]
int sz6 = random.Next(71)-100;
// [-12, -3]
int sz7 = random.Next(10)-12;

/*
 2 véletlen számot generáljunk [0,10], 
és irjuk ki a számokat
a képernyőre, majd azt hogy melyik szám a nagyobb, 
plusz ha egyenlő azt is irjuk ki. 
 */

Random random1 = new Random();
int num1 = random1.Next(11);
int num2 = random1.Next(11);
Console.WriteLine(num1);
Console.WriteLine(num2);
if (num1>num2) Console.WriteLine($"{num1} a nagyobb");
else if (num2 > num1) Console.WriteLine($"{num2} a nagyobb");
else Console.WriteLine("A két szám egyforma");


/*
 Generálj random [1,10], ird ki az erdeményt, 
és döntsd el hogy a kapott szám az páros vagy páratlan
 */

Random random2 = new Random();
int num3 = random2.Next(10) +1;
if (num3 % 2 == 0) Console.WriteLine($"A(z) {num3} páros");
else Console.WriteLine($"A(z) {num3} páratlan");


/*
 kő, papír, olló játék-->6%, viszont aki 9sor alatt megoldja, az 5-ös
1-->kő
2-->papír
3-->olló

generáljon gép [1,3] között random számot
kérjen be a felh-tól is [1,3] között egy számot
ki is kell íratni, hogy ki mit választott SZÖVEGESEN

a logikát irjuk meg if else-ben vagy a hármas operandussal
 */

// egy lehetséges megoldás:
Random random10 = new Random();
int gepSzam = random10.Next(3) + 1;
Console.WriteLine("Adj egy számot (1-3)[kő, papír, olló]");
int felhSzam = Convert.ToInt32(Console.ReadLine());
// kiíratom a gép mire gondolt
Console.Write("Gép: ");
switch (gepSzam)
{
	case 1: Console.WriteLine("KŐ"); break;
	case 2: Console.WriteLine("Papír"); break;
	case 3: Console.WriteLine("Olló"); break;
}
// kiíratom, hogy a felh. mire gondolt
Console.Write("Felh: ");
switch (felhSzam)
{
	case 1: Console.WriteLine("KŐ"); break;
	case 2: Console.WriteLine("Papír"); break;
	case 3: Console.WriteLine("Olló"); break;
}

if (gepSzam == felhSzam) Console.WriteLine("Döntetlen");
else if (gepSzam == 1 && felhSzam == 3
	|| gepSzam == 2 && felhSzam == 1
	|| gepSzam == 3 && felhSzam == 2
	) Console.WriteLine("gép győzött");
else Console.WriteLine("én nyertem");

/*
 a, b, c oldal generáljuk le [10,80], szerkeszthető hármoszög-e
mikor? Amikor ezek igazak: (a+b>c) és (a+c>b) és (b+c>a)
 */

Random random3 = new Random();
int a = random3.Next(71) + 10;
int b = random3.Next(71) + 10;
int c = random3.Next(71) + 10;

if((a + b > c)  &&(a + c > b) &&(b + c > a)){
	Console.WriteLine("igen");
}else
{
	Console.WriteLine("nem");
}
```
