using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace The_Better_Music_Producer
{
    class The_Better_Music_Producer
    {
        static void Main(string[] args)
        {
            short albums_eu = short.Parse(Console.ReadLine());
            double price_eu = double.Parse(Console.ReadLine());
            short albums_us = short.Parse(Console.ReadLine());
            double price_us = double.Parse(Console.ReadLine());
            short albums_sa = short.Parse(Console.ReadLine());
            double price_sa = double.Parse(Console.ReadLine());

            short number_concerts = short.Parse(Console.ReadLine());
            double profit_single_concert = double.Parse(Console.ReadLine());


            double profit_eu = albums_eu * price_eu * 1.94;
            double profit_us = albums_us * price_us * 1.72;
            double profi_sa = albums_sa * price_sa / 332.74;
            double producer_benefit = (profit_eu + profit_us + profi_sa) * 65 / 100;
            double producer_benefit_albums = producer_benefit * 80 / 100;

            double concerts_profit = number_concerts * profit_single_concert * 1.94;
            if (concerts_profit > 100000)
                concerts_profit -= concerts_profit * 15 / 100;
            if (concerts_profit >= producer_benefit_albums)
                Console.WriteLine($"On the road again! We'll see the world and earn {concerts_profit:f2}lv.");
            else
                Console.WriteLine($"Let's record some songs! They'll bring us {producer_benefit_albums:f2}lv.");

        }
    }
}
