# Other-Vacation
Just another repository
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Vacation
{
    class Vacation
    {
        static void Main(string[] args)
        {
            int adult = int.Parse(Console.ReadLine());
            int kids = int.Parse(Console.ReadLine());
            int night = int.Parse(Console.ReadLine());
            string transport = Console.ReadLine();

            decimal adultPrice = 0;
            decimal kidsPrice = 0;
            int group = adult + kids;

            switch (transport)
            {
                case "train": adultPrice = adult * 24.99m; kidsPrice = kids * 14.99m;
                    if (group >= 50)
                    {
                        adultPrice *= 0.50m;
                        kidsPrice *= 0.50m;
                    }
                    break;
                case "bus": adultPrice = adult * 32.50m; kidsPrice = kids * 28.50m; break;
                case "boat": adultPrice = adult * 42.99m; kidsPrice = kids * 39.99m; break;
                case "airplane": adultPrice = adult * 70.00m; kidsPrice = kids * 50.00m; break;
            }

            decimal allTickets = adultPrice + kidsPrice;
            allTickets *= 2.00m;

            decimal hotel = night * 82.99m;

            decimal allCosts = hotel + allTickets;
            allCosts *= 1.10m;

            Console.WriteLine($"{allCosts:f2}");
        }
    }
}
