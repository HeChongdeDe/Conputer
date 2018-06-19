# Conputer


using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;

namespace counter
{
    class Program
    {
        static void Main(string[] args)
        {
            //定义两个数
            int x, y,result=0;
            //键盘输入这两个数,对输入错误进行报错
            Console.WriteLine("请输入第一个数：");
            x = Get_n();
            Console.WriteLine("请输入第二个数：");
            y = Get_n();
            //定义一个字符
            string c;
            //输入该字符
            Console.WriteLine("请输入需要的运算符（+ - * /）：");
            int a=0;
            while (a < 10)
            {
                a = 100;
                c = Console.ReadLine();
                //判断字符（+ - * / 其他） //进行指定运算（异常处理）
                switch (c)
                {
                    case "+": result = x + y; break;
                    case "-": result = x - y; break;
                    case "*": result = x * y; break;
                    case "/":
                        try
                        {
                            result = x / y;
                        }
                        catch(DivideByZeroException)
                        {
                            Console.WriteLine("除数不能为零!");
                            return;
                        }
                        break;
                    default: Console.WriteLine("输入运算符异常！请重新输入："); a = 0; break;
                }
            }
            //输出结果
           Console.WriteLine("计算结果为："+result);
        }
        static int Get_n()  //防止//static 静态成员，若果不写则函数需要对象引用。    函数与函数对应，在main外部写
        {
            try
            {
                string s=Console.ReadLine();  //读取一行字符串
                int x=Convert.ToInt32(s);  //将字符串转换为想要的类型
                return x;
            }
            catch
            {
                Console.WriteLine("输入的数据有误，重新输入：");
                return Get_n();
            }
        }

    }
}
