```c#
// random
Random r = new Random();
int sz = r.Next(9); //[0,8]
// [2,8]
int sz1 = r.Next(7)+2;
// [3,5]
int sz2 = r.Next(3)+3;
// [-2,5]
int sz3 = r.Next(8)-2;
// [-10, 10]
int sz4 = r.Next(21)-10;
// [-20,-4]
int sz5 = r.Next(17)-20;
// [-10,-2]
int sz6 = r.Next(9)-10;

// generáljunk 3 random számot [-100, 50],
// majd írja ki értéküket

Random r2 = new Random();
int szam1 = r2.Next(151)-100;
int szam2 = r2.Next(151)-100;
int szam3 = r2.Next(151)-100;
Console.WriteLine($"{szam1} {szam2} {szam3}");

// megcserélni a szam2 értéket a szám3-al
// és irjuk ki újra mind a 3 értékét
int temp = szam2;
szam2 = szam3;
szam3 = temp;
Console.WriteLine($"{szam1} {szam2} {szam3}");

// megnézzük, hogyan lehet számokat növekvő sorrendbe
// cserélgetni


Console.WriteLine($"{szam1} {szam2} {szam3}");
if (szam1 > szam2)
{
	int temp2 = szam1;
	szam1 = szam2;
	szam2 = temp2;
}
if (szam1 > szam3)
{
	int temp2 = szam1;
	szam1 = szam3;
	szam3 = temp2;
}
if (szam2 > szam3)
{
	int temp2 = szam2;
	szam2 = szam3;
	szam3 = temp2;
}
Console.WriteLine($"{szam1} {szam2} {szam3}");

// most már tudjuk hogy melyik a legnagyobb és melyik a legkissebb
// írjuk ki őket

Console.WriteLine($"Legnagyobb: {szam3}");
Console.WriteLine($"Legkissebb: {szam1}");

//----------------------------------------------------------------
// CIKLUSOK (elöl és hátul tesztelős)
// WHILE, elöl tesztelős, akkor fut le has a feltétel igaz
// és addig fut AMÍG a feltétel igaz

int szam = 6;


while (szam < 8)
{
	Console.WriteLine("A feltétel igaz");
}

// DO-WHILE, hátul tesztelős, mindenféleképpen lefut egyszer,
// utánna viszont addig fut, AMÍG a feltétel igaz

do
{
	Console.WriteLine("A feltétel igaz");
} while (szam<3);


// hozzunk létre egy ciklusváltozót amit
// a ciklusmagban folyamatosan növeljük
// eglészen addig míg a szám el nem éri a 10-et

int ciklusvaltozo = 0;
while (ciklusvaltozo < 10)
{
	ciklusvaltozo++;
	Console.WriteLine(ciklusvaltozo);
}

// végezzünk egy kiíratást 5-10ig
int ciklusvaltozo2 = 4;
while (ciklusvaltozo2 < 10)
{
	ciklusvaltozo2++;
	Console.WriteLine(ciklusvaltozo2);
}
```
