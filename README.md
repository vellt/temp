```c#
string fanta = "fanta";
string cola = "cola";
string ures = "ures";
ures = fanta;
fanta = cola;
cola = ures;


// szám csere
int sz1 = 5;
int sz2 = 10;
int ures1 = 0;
ures1 = sz1;
sz1 = sz2; // 10
sz2 = ures1; // 5

/* 
 * kérd be az 'a' értéket és a 'b' értéket a felh-tól, és 
 * Íratsd őket ki, majd cseréld meg az értéküket, és megint
 * íratsd ki az 'a' és a 'b' változót
 */

Console.WriteLine("Add meg az 'a' értékét:");
int a = Convert.ToInt32(Console.ReadLine());

Console.WriteLine("Add meg az 'b' értékét:");
int b = Convert.ToInt32(Console.ReadLine());

Console.WriteLine($"Az a={a}, b={b}");

int temp = a;
a = b;
b = temp;

Console.WriteLine($"Az a={a}, b={b}");

/*
 legyen 3 változó
szam1, szam2, szam3
pl ezekkel az értékekkel
sza1=5;
sza2=4;
szam3=3;

ezt kell úgy átcserélgetni, hogy növekvő sorrenbe kerüljön
 */
Random r = new Random();
int szam1 = r.Next(31) + 20; //[20,50]
int szam2 = r.Next(31) + 20;
int szam3 = r.Next(31) + 20;
Console.WriteLine($"{szam1} {szam2} {szam3}");
if (szam1 > szam2)
{
	int temp1 = szam1;
	szam1 = szam2;
	szam2 = temp1;
}
if(szam1 > szam3)
{
	int temp1 = szam1;
	szam1 = szam3;
	szam3 = temp1;
}
if (szam2 > szam3)
{
	int temp1 = szam2;
	szam2 = szam3;
	szam3 = temp1;
} 
Console.WriteLine($"{szam1} {szam2} {szam3}");

/*
 3 random szám [5,10]
statisztika:
- mennyi páros
- mennyi páratlan
- mennyi az átlaguk
- mennyi az összegük
- rendezzük sorba őket
- mi a max érték
- mi a min érték
 */
Random r1 = new Random();
int s1 = r1.Next(6) + 5;
int s2 = r1.Next(6) + 5;
int s3 = r1.Next(6) + 5;
Console.WriteLine("Statisztika");
Console.WriteLine($" {s1} {s2} {s3}");
int parosSzamlalo = 0;
int paratlanSzamlalo = 0;
if (s1 % 2 == 0) parosSzamlalo++;
else paratlanSzamlalo++;
if (s2 % 2 == 0) parosSzamlalo++;
else paratlanSzamlalo++;
if (s3 % 2 == 0) parosSzamlalo++;
else paratlanSzamlalo++;
Console.WriteLine($"páros számok: {parosSzamlalo} db");
Console.WriteLine($"páratlan számok: {paratlanSzamlalo} db");
Console.WriteLine($"összegük: {s1 + s2 + s3} db");
// növekvő sorba rendezés
int tempV = 0;
if (s1 > s2)
{
	tempV = s1;
	s1 = s2;
	s2 = temp;
}
if(s1 > s3)
{
	tempV = s1;
	s1 = s3;
	s3 = tempV;
}
if (s2 > s3)
{
	tempV = s2;
	s2 = s3;
	s3 = s2;
}
Console.WriteLine($" {s1} {s2} {s3}");
Console.WriteLine($"Max: {s3}");
Console.WriteLine($"Min: {s1}");
Console.WriteLine($"átlaguk: {(s1+s2+s3)/3.0}");
```
