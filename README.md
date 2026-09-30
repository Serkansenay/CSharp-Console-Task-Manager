using System;
using System.Collections.Generic;

namespace TaskManager
{
    class Program
    {
        static void Main(string[] args)
        {
            List<string> tasks = new List<string>();
            bool isRunning = true;

            Console.WriteLine("--- Görev Yöneticisine Hoş Geldiniz ---");

            while (isRunning)
            {
                Console.WriteLine("\n1. Yeni Görev Ekle | 2. Görevleri Listele | 3. Çıkış");
                Console.Write("Seçiminiz: ");
                string choice = Console.ReadLine();

                switch (choice)
                {
                    case "1":
                        Console.Write("Eklenecek görevi yazın: ");
                        string newTask = Console.ReadLine();
                        if (!string.IsNullOrWhiteSpace(newTask))
                        {
                            tasks.Add(newTask);
                            Console.WriteLine("✅ Görev başarıyla eklendi.");
                        }
                        break;
                    case "2":
                        Console.WriteLine("\n--- Mevcut Görevleriniz ---");
                        if (tasks.Count == 0)
                        {
                            Console.WriteLine("Henüz hiç görev eklenmemiş.");
                        }
                        else
                        {
                            for (int i = 0; i < tasks.Count; i++)
                            {
                                Console.WriteLine($"[{i + 1}] {tasks[i]}");
                            }
                        }
                        break;
                    case "3":
                        isRunning = false;
                        Console.WriteLine("Çıkış yapılıyor...");
                        break;
                    default:
                        Console.WriteLine("❌ Geçersiz seçim, lütfen tekrar deneyin.");
                        break;
                }
            }
        }
    }
}
