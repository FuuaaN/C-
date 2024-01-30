# C# Console Uygulamaları

Bu depoda C# programlama dili kullanılarak geliştirilmiş bazı basit console uygulamalarını bulabilirsiniz. Aşağıda, her bir örneği kısa açıklamalar ve örnek kodları ile bulabilirsiniz.

## Dizi Sıralama Programı

### Klavyeden girilen n elemanlı bir diziyi küçükten büyüğe sıralayan bir program örneği.

    Console.WriteLine("Dizi Kaç Elemanlı Olsun? ");
    int n = Convert.ToInt32(Console.ReadLine());
    
    int[] dizi = new int[n];
    int a = 1;
    
    for (int i = 0; i < n; i++)
    {
        Console.WriteLine("{0}.Dizi Elemanını Giriniz: " , a);
        dizi[i] = Convert.ToInt32(Console.ReadLine());
        a++;
    }
    int x;
    
    for (int i = 0; i < n; i++)
    {
        for (int j = 0; j < i; j++)
        {
            if (dizi[i] < dizi[j])
            {
                x = dizi[j];
                dizi[j] = dizi[i];
                dizi[i] = x;
            }
        }
    }
    Console.Write("Küçükten Büyüğe Sıralanmış Dizi: ");
    foreach (int ek in dizi)
    {
        Console.Write(ek + " ");
    }


### Kenar Uzunluğu Girilen Dikdörtgenin Alan ve Çevresini Yazdıran Console Örneği

    Console.WriteLine("Dikdörtgenin Uzun kenar uzunluğunu giriniz: ");
    int uk = Convert.ToInt32(Console.ReadLine());
    
    Console.WriteLine("Dikdörtgenin Kısa kenar uzunluğunu giriniz: ");
    int kk = Convert.ToInt32(Console.ReadLine());
    
    double alan = uk * kk;
    int cevre = (kk + uk) * 2;
    
    Console.WriteLine("Dikdörtgenin Alanı: " + alan);
    Console.WriteLine("Dikdörtgenin Çevresi: "  + cevre);

### 0 ile 100 arası rastgele girilen bir sayıyı tahmin etme oyunu

    Random rnd = new Random();
    
    int x = rnd.Next(0 , 100);
    int sayac = 0;
    
    Console.WriteLine("Tahmininiz Nedir?");
    while (true)
    {
        
        int tahmin = Convert.ToInt32(Console.ReadLine());
        sayac++;
    
        if (x < tahmin)
        {
            Console.Write("Daha Küçük Bir Sayı Giriniz: ");
        }
        else if (x > tahmin)
        {
            Console.Write("Daha Büyük Bir Sayı Giriniz: ");
        }
        else if (x == tahmin)
        {
            Console.WriteLine("Tebrikler! Sayıyı {0}.Denemede Buldunuz: " + x , sayac);
        }
    }


### Kenar Uzunluğu Girilen Dikdörtgenin Alan ve Çevresini Yazdıran Console Örneği

    Console.WriteLine("Kısa Kenar Uzunluğu Giriniz: ");
    int kk = Convert.ToInt32(Console.ReadLine());
    
    Console.WriteLine("Uzun Kenarı Giriniz :");
    int uk = Convert.ToInt32(Console.ReadLine());
    
    double cevre = (kk + uk) * 2;
    double alan = kk * uk;
    
    if (kk < uk)
    {
        Console.WriteLine("Dikdörtgenin Çevresi: " + cevre);
        Console.WriteLine("Dikdörtgenin Alanı: " + alan);
    }
    else if (kk > uk) Console.WriteLine("Hatalı Giriş Mal! Kısa Kenar Uzun Kenardan Büyük Olur Mu?");

### 20 Elemanlı Random Dizi Oluşturup, Elemanlarını Bulduran Program

    Random rnd = new Random();
    
    int[] dizirnd = new int[20];
    
    int sayac = 1 , indis = 0 , tur = 1;
    
    for (int i = 0; i < 20; i++)
    {
        dizirnd[i] = rnd.Next(0 , 100);
    }
    while (true)
    {
        Console.WriteLine("Bir Sayı Giriniz: ");
        int tahmin = Convert.ToInt32(Console.ReadLine());
        
        for (int j = 0;j < dizirnd.Length; j++)
        {
            if (tahmin == dizirnd[j])
            {
                sayac++;
                indis = j;
            }
        }
        
        if (sayac == 1)
        {
            Console.WriteLine("Bulunamadı");
            tur ++;
        }
        else
        {
            Console.WriteLine("{0}.Eleman Olarak Bulundu ({1}.Deneme): " + tahmin , indis , tur);
            break;
        }
    }

### Kullanıcının girdiği 10 sayıdan 50 den küçük olanların adetini bulan ve gösteren console örneği

    int sayi = 0 , j = 1 , sayac = 0;
    
    for (int i = 0; i < 10; i++)
    {
        Console.Write("{0}.Sayıyı Giriniz: " , j);
        sayi = Convert.ToInt32(Console.ReadLine());
        j++;
    
        if (sayi < 50)
        {
            sayac++;
        }
    }
    Console.Write("50 Den Küçük Sayı Adeti: " + sayac);

### Klavyeden Girilen Sayının Asal Olup Olmadığını Bulan Program;

    while (true)
    {
    int sayac = 0;
    char secim;
    
    Console.WriteLine("Sayıyı Girin");
    int sayi = Convert.ToInt32(Console.ReadLine());
    
    for(int i = 1; i <= sayi; i++)
    {
        if (sayi % i == 0)
        {
            sayac++;
        }
    }
    
    if (sayac == 2)
    {
        Console.WriteLine("Girdiğiniz {0} Sayısı Asal Bir Sayıdır." , sayi);
    }
    else
    {
        Console.WriteLine("Girdiğiniz {0} Sayısı Asal Bir Sayı Değildir." , sayi);
    }
    Console.WriteLine("Devam Etmek İstiyor musunuz? (E / H)");
    secim = Convert.ToChar(Console.ReadLine());
    
    if (secim == 'H' || secim == 'h')  break;
    }

### Klavyeden Girilen Dizinin En Büyük , En Küçük Elemanını ve İndisini Bulma;

    Console.WriteLine("Diziniz kaç elemanlı olsun?");
    int n = Convert.ToInt32(Console.ReadLine());
    
    int[] dizi = new int[n];
    
    int eleman = 0 , ebi = 0 , eki = 0;
    
    for(int i = 0;i < dizi.Length;i ++)
    {
        int j = i+1;
        Console.WriteLine("{0}.Elemanı giriniz: ", j);
        eleman = Convert.ToInt32(Console.ReadLine());
        dizi[i] = eleman;
    }
    int eb = dizi[0] , ek = dizi[0];
    
    for(int x = 0; x < dizi.Length;x ++)
    {   
        if(dizi[x] < ek)
        {
            ek = dizi[x];
            eki = x;
        }
        else if(dizi[x] > eb)
        {
            eb = dizi[x];
            ebi = x;
        }
    }
    Console.WriteLine("Dizinin en büyük elemanı: " + eb);
    Console.WriteLine("Dizinin en büyük indisi: " + ebi);
    Console.WriteLine("Dizinin en küçük elemanı: " + ek);
    Console.WriteLine("Dizinin en küçük indisi: " + eki);

### Vize Final Hesaplama;

    int vize , final;
    
        Console.Write("Vize: ");
        vize = int.Parse(Console.ReadLine());
    
        Console.Write("Final: ");
        final = int.Parse(Console.ReadLine());
    
    if ((vize >= 0 && vize <= 100) && (final >= 0 && final >= 100))
    {
        double ort = vize * 0.4 + final * 0.6;
    
        if (ort >= 50 && ort <= 100 && final >= 50)
        {
            Console.WriteLine("GEÇTİ!" + " " + "Ortalama: " + ort);
        }
        else
        {
            Console.WriteLine("KALDI!" + " " + "Ortalama: " + ort);
        }
    }
    else
    {
        Console.WriteLine("HATALI GİRİŞ!!!");
    }

### Klavyeden girilen 10 elemanlı bir dizinin elemanlarını %20 arttıran ve ekrana yazdıran örnek:

    double[] dizi = new double[10];
    int j = 1;
    
    for (int i = 0; i < 10; i++)
    {
        Console.Write("Dizinin {0}.Elemanını Giriniz: " , j);
        dizi[i] = double.Parse(Console.ReadLine());
    
        dizi[i] = dizi[i] * 20 / 100;
        j++;
    }
    Console.WriteLine("Girdiğiniz Elemanların %20'si:");
    int a = 1;
    
    foreach (int i in dizi)
    {
        Console.WriteLine("{0}.Eleman: " + i , a);
        a++;
    }
