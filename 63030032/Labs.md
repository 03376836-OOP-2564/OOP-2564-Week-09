# การทดลอง #

## การทดลอง 9.1  Fields ##

1. ให้พิจารณา code ด้านล่างนี้ นักศึกษาคิดว่าผลการรันจะเป็นอย่างไร 
   
```

  [ให้เขียนความคาดหมายผลที่จะได้ตรงนี้]
  โปรแกรมจะเรียกใช้งาน class Program เป็นอันดับแรก เพราะมี static void Main() อยู่ใน class จากนั้นจะทำการสร้างตัวแปร mc มาเก็บค่าของ 
   class Myclass ที่ประกาศสร้างมาใหม่ จากนั้นจะแสดงข้อมูลที่อยู่ใน class Myclass ผ่าน Command Line ซึ่งจะแสดงผลออกเป็นเลข 0 และค่า null
   
```   


```csharp
using System;

namespace method_examples
{
    class MyClass
    {
        // Non numeric = 2 types
        public bool myBool;
        public char myChar;

        // Integer = 8 types
        public byte myByte;
        public sbyte mySbyte;
        public short myShort;
        public ushort myUShort ;
        public int myInt;
        public uint myUInt;
        public long myLong;
        public ulong myULong;

        // Floating point = 3 types
        public float myFloat;
        public double myDouble;
        public decimal myDecimal;

        // Others = 3 types
        public string myString;
        public object myObject;
        public dynamic myDynamic;

    }

    class Program
    {
        static void Main()
        {
            MyClass mc = new MyClass();
            Console.WriteLine("Non numeric types default value.");
            Console.WriteLine($"Default value of Bool   \t: {mc.myBool}");
            Console.WriteLine($"Default value of Char   \t: {mc.myChar}");
            Console.WriteLine($"-------------------------");
            Console.WriteLine("Integer types default value.");
            Console.WriteLine($"Default value of Sbyte  \t: {mc.mySbyte}");
            Console.WriteLine($"Default value of Byte   \t: {mc.myByte}");
            Console.WriteLine($"Default value of Short  \t: {mc.myShort}");
            Console.WriteLine($"Default value of UShort \t: {mc.myUShort}");
            Console.WriteLine($"Default value of Int    \t: {mc.myInt}");
            Console.WriteLine($"Default value of UInt   \t: {mc.myUInt}");
            Console.WriteLine($"Default value of Long   \t: {mc.myLong}");
            Console.WriteLine($"Default value of ULong  \t: {mc.myULong}");
            Console.WriteLine($"-------------------------");
            Console.WriteLine("Floating point types default value.");
            Console.WriteLine($"Default value of Float  \t: {mc.myFloat}");
            Console.WriteLine($"Default value of Double \t: {mc.myDouble}");
            Console.WriteLine($"Default value of Decimal\t: {mc.myDecimal}");
            Console.WriteLine($"-------------------------");
            Console.WriteLine("Others predefined types default value.");
            Console.WriteLine($"Default value of String \t: {mc.myString}");
            Console.WriteLine($"Default value of Object \t: {mc.myObject}");
            Console.WriteLine($"Default value of Dynamic\t: {mc.myDynamic}");
        }
    }
}
```

2. สร้าง project แล้วรันโปรแกรม

```
   โปรแกรมจะแสดงข้อมูลที่อยู่ใน class MyClass ผ่าน Command Line ดังภาพด้านล่าง ตัวแปรที่แสดงผลออกมาจะเป็นเลข 0 และค่า null
```
3. บันทึกผล
```

  [บันทึกผล]
   
``` 
![Screenshot 2022-05-16 023726](https://user-images.githubusercontent.com/92078816/168490868-542fa2da-8bc3-43c5-b72d-333aa15be46f.png)



4. ผลที่ได้เหมือนหรือต่างจากที่คิดไว้อย่างไร  
```

  [ให้เขียนบรรยายตรงนี้]
    ตรงกับสิ่งที่คิดไว้ เพราะ เราไม่ได้ทำการกำหนดค่าให้ตัวแปรใน class MyClass ตัวคอมไพเลอร์เลยกำหนดค่าเริ่มต้นให้ตัวแปรเป็น 0 หรือเป็นค่า null
```   

## การทดลอง 9.2  Access Modifiers ##
1. ให้พิจารณาโปรแกรมต่อไปนี้ นักศึกษาคาดว่าผลการทำงานจะเป็นเช่นไร

```

  [ให้เขียนความคาดหมายผลที่จะได้ตรงนี้]
    น่าจะไม่สามารถทำงานได้ เพราะมีการเรียกใช้ค่าของ private และ protected
```   



```cs

using System;

namespace method_examples
{
    class ATM 
    {
        // access modifiers
        public int IntPublic;
        private int IntPrivate;
        protected int IntProtected;
        internal int IntInternal;
        protected internal int IntProtectedInternal;
    }

    class Program
    {
        static void Main()
        {
            ATM atm1;            // สร้าง reference
            atm1 = new ATM();   // สร้าง instance และ assign ให้กับ reference

            // สร้าง instance และ reference พร้อมทั้ง assign ให้แก่ reference
            ATM atm2 = new ATM();

            atm1.IntPublic = 10;
            atm1.IntPrivate = 10;
            atm1.IntProtected = 10;
            atm1.IntInternal = 10;
            atm1.IntProtectedInternal = 10;
            Console.WriteLine($"IntPublic = {atm1.IntPublic}");
            Console.WriteLine($"IntPrivate = {atm1.IntPrivate}");
            Console.WriteLine($"IntProtected = {atm1.IntProtected}");
            Console.WriteLine($"IntInternal = {atm1.IntInternal}");
            Console.WriteLine($"IntProtectedInternal = {atm1.IntProtectedInternal}");


        }
    }
}

```
2. สร้าง project แล้วรันโปรแกรม
3. บันทึกผล
```
โปรแกรมไม่สามารถรันได้เกิดปัญหาดังภาพด้านล่าง   
```   
![Screenshot 2022-05-16 024433](https://user-images.githubusercontent.com/92078816/168491121-80675b11-bd03-427e-8dda-be3228483be6.png)


4. ผลที่ได้เหมือนหรือต่างจากที่คิดไว้อย่างไร  
```
เหมือนกับที่คิดไว้ เพราะโปรแกรมมีการเรียกใช้ค่าของ private และ protected ใน class ATM ซึ่งตัวแปรที่เป็นค่า private และ protected จะใช้ได้แค่ในclass ของมัน ไม่สามารถถูกเรียกใช้โดย class อื่นได้
   
```   
