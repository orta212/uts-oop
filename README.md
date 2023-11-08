```c#
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace OOP6
{
    public class Pegawai
    {
        private string nama;
        private double gajiPokok;

        //setter getter nama
        public void setNama(string nama){ this.nama = nama;}

        public string getNama(){ return this.nama;}
        
        //setter getter gajiPokok
        public double getGajiPokok(){ return this.gajiPokok;}
        
        public void setGajiPokok(double gajiPokok){ this.gajiPokok = gajiPokok;}
        
        //other
        public void cetakInfo()
        {
            Console.WriteLine("Nama : " + this.nama);
        }
        
    }

    public class Manager : Pegawai
    {
        private double tunjangan;

        public void setTunjangan(double tunjangan){this.tunjangan = tunjangan;}
        public double getTunjangan(){return this.tunjangan;}
        public new void cetakInfo()
        {
            base.cetakInfo();
            Console.WriteLine("Gaji Pokok : Rp." + this.getGajiPokok());
            Console.WriteLine("Posisi : Manager");
            this.cetakTunjangan();
        }
        public void cetakTunjangan()
        {
            Console.WriteLine("Tunjangan : Rp." + this.tunjangan);
        }

    }

    public class Programmer : Pegawai
    {
        private double bonus;

        //setter getter Bonus
        public void setBonus(double bonus){ this.bonus = bonus;}

        public double getBonus(){ return this.bonus;}

        public new void cetakInfo()
        {
            base.cetakInfo();
            Console.WriteLine("Posisi : Programmer");
            this.cetakBonus();
        }
        public void cetakBonus()
        {
            Console.WriteLine("Bonus : Rp." + this.bonus);            
        }


    }
}

```

```C#
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace OOP6
{
    class Program
    {
        public static void Main(string[] args)
        {   
            Manager Anton = new Manager();
            Anton.setNama("Anton");
            Anton.setGajiPokok(14000000);
            Anton.setTunjangan(35000000);
            Anton.cetakInfo();

            Console.WriteLine("\n \n");
            Programmer Budi = new Programmer();
            Budi.setNama("Budi");
            Budi.setGajiPokok(14000000);
            Budi.setBonus(35000000);
            Budi.cetakInfo();
        }
    }
}
```
