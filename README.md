////using System;
////using System.Collections.Generic;
////using System.Linq;
////using System.Text;
////using System.Threading.Tasks;

////namespace ABC
////{




////    /// Polymorphism and Abstract Classes
////    /// 



////    class Base
////    {
////        // Create virtual method in the base class.
////        public virtual void Who()
////        {
////            Console.WriteLine("Who() in Base");
////        }
////    }
////    class Derived1 : Base
////    {
////        // Override Who() in a derived class.
////        public override void Who()
////        {
////            Console.WriteLine("Who() in Derived1");
////        }
////    }

////    class Derived2 : Base
////    {
////        // Override Who() again in another derived class.
////        public override void Who()
////        {
////            Console.WriteLine("Who() in Derived2");
////        }
////    }
////    internal class Program
////    {
////        static void Main(string[] args)
////        {
////            Base baseOb = new Base();
////            Derived1 dOb1 = new Derived1();
////            Derived2 dOb2 = new Derived2();
////            Base baseRef; // a base class reference
////            baseRef = baseOb;
////            baseRef.Who();
////            baseRef = dOb1;
////            baseRef.Who();
////            baseRef = dOb2;
////            baseRef.Who();
////        }
////    }
////}


//using System;
//class Base
//{
//    // Create virtual method in the base class.
//    public virtual void Who()
//    {
//        Console.WriteLine("Who() in Base");
//    }
//}
//class Derived1 : Base
//{
//    // Override Who() in a derived class.
//    public override void Who()
//    {
//        Console.WriteLine("Who() in Derived1");
//    }
//}
//class Derived2 : Derived1
//{
//    // This class also does not override Who().
//}
//class Derived3 : Derived2
//{
//    // This class does not override Who().
//}

//namespace PolymorphismTest
//{
//    class Program
//    {
//        static void Main(string[] args)
//        {
//            Derived3 dOb = new Derived3();
//            Base baseRef; // a base class reference
//            baseRef = dOb;
//            baseRef.Who(); // calls Derived1's Who()
//        }
//    }
//}



/*
using System;

class TwoDShape
{
    double pri_width;
    double pri_height;
    // A default constructor.
    public TwoDShape()
    {
        Width = Height = 0.0;
        name = "null";
    }
    // Parameterized constructor.
    public TwoDShape(double w, double h, string n)
    {
        Width = w;
        Height = h;
        name = n;
    }
    // Construct object with equal width and height.
    public TwoDShape(double x, string n)
    {
        Width = Height = x;
        name = n;
    }
    // Construct a copy of a TwoDShape object.
    public TwoDShape(TwoDShape ob)
    {
        Width = ob.Width;
        Height = ob.Height;
        name = ob.name;
    }
    // Properties for Width and Height.
    public double Width
    {
        get { return pri_width; }
        set { pri_width = value < 0 ? -value : value; }
    }
    public double Height
    {
        get { return pri_height; }
        set { pri_height = value < 0 ? -value : value; }
    }
    public string name { get; set; }
    public void ShowDim()
    {
        Console.WriteLine("Width and height are " +
        Width + " and " + Height);
    }
    public virtual double Area()
    {
        Console.WriteLine("Area() must be overridden");
        return 0.0;
    }
}



// A derived class of TwoDShape for triangles.
class Triangle : TwoDShape
{
    string Style;
    // A default constructor.
    public Triangle()
    {
        Style = "null";
    }
    // Constructor for Triangle.
    public Triangle(string s, double w, double h) :
        base(w, h, "triangle")
    {
        Style = s;
    }
    // Construct an isosceles triangle.
    public Triangle(double x)
        : base(x, "triangle")
    {
        Style = "isosceles";
    }
    // Construct a copy of a Triangle object.
    public Triangle(Triangle ob)
        : base(ob)
    {
        Style = ob.Style;
    }
    // Override Area() for Triangle.
    public override double Area()
    {
        return Width * Height / 2;
    }
    // Display a triangle's style.
    public void ShowStyle()
    {
        Console.WriteLine("Triangle is " + Style);
    }
}

// A derived class of TwoDShape for rectangles.
class Rectangle : TwoDShape {
// Constructor for Rectangle.
public Rectangle(double w, double h) :
base(w, h, "rectangle"){ }
// Construct a square.
public Rectangle(double x) :
    base(x, "rectangle") { }
// Construct a copy of a Rectangle object.
public Rectangle(Rectangle ob) : base(ob) { }
// Return true if the rectangle is square.
public bool IsSquare()
{
    if (Width == Height) return true;
    return false;
}
// Override Area() for Rectangle.
public override double Area()
{
    return Width * Height;
}
}
namespace PolymorphismTest
{
    class Program
    {
        static void Main(string[] args)
        {
            TwoDShape[] shapes = new TwoDShape[5];
            shapes[0] = new Triangle("right", 8.0, 12.0);
            shapes[1] = new Rectangle(10);
            shapes[2] = new Rectangle(10, 4);
            shapes[3] = new Triangle(7.0);
            shapes[4] = new TwoDShape(10, 20, "generic");
            for (int i = 0; i < shapes.Length; i++)
            {
                Console.WriteLine("object is " + shapes[i].name);
                Console.WriteLine("Area is " + shapes[i].Area());
                Console.WriteLine();
            }
        }
    }
}
*/

////////////////////////////////Abstract Classes
///


/*
using System;

///
abstract class TwoDShape
{
    double pri_width;
    double pri_height;
    // A default constructor.
    public TwoDShape()
    {
        Width = Height = 0.0;
        name = "null";
    }
    // Parameterized constructor.
    public TwoDShape(double w, double h, string n)
    {
        Width = w;
        Height = h;
        name = n;
    }
    // Construct object with equal width and height.
    public TwoDShape(double x, string n)
    {
        Width = Height = x;
        name = n;
    }
    // Construct a copy of a TwoDShape object.
    public TwoDShape(TwoDShape ob)
    {
        Width = ob.Width;
        Height = ob.Height;
        name = ob.name;
    }
    // Properties for Width and Height.
    public double Width
    {
        get { return pri_width; }
        set { pri_width = value < 0 ? -value : value; }
    }
    public double Height
    {
        get { return pri_height; }
        set { pri_height = value < 0 ? -value : value; }
    }
    public string name { get; set; }
    public void ShowDim()
    {
        Console.WriteLine("Width and height are " +
        Width + " and " + Height);
    }
    // Now, Area() is abstract.
    public abstract double Area();
}

// A derived class of TwoDShape for triangles.
class Triangle : TwoDShape
{
    string Style;
    // A default constructor.
    public Triangle()
    {
        Style = "null";
    }
    // Constructor for Triangle.
    public Triangle(string s, double w, double h) :
        base(w, h, "triangle")
    {
        Style = s;
    }
    // Construct an isosceles triangle.
    public Triangle(double x)
        : base(x, "triangle")
    {
        Style = "isosceles";
    }
    // Construct a copy of a Triangle object.
    public Triangle(Triangle ob)
        : base(ob)
    {
        Style = ob.Style;
    }
    // Override Area() for Triangle.
    public override double Area()
    {
        return Width * Height / 2;
    }
    // Display a triangle's style.
    public void ShowStyle()
    {
        Console.WriteLine("Triangle is " + Style);
    }
}

// A derived class of TwoDShape for rectangles.
class Rectangle : TwoDShape
{
    // Constructor for Rectangle.
    public Rectangle(double w, double h) :
        base(w, h, "rectangle")
    { }
    // Construct a square.
    public Rectangle(double x) :
        base(x, "rectangle")
    { }
    // Construct a copy of a Rectangle object.
    public Rectangle(Rectangle ob) : base(ob) { }
    // Return true if the rectangle is square.
    public bool IsSquare()
    {
        if (Width == Height) return true;
        return false;
    }
    // Override Area() for Rectangle.
    public override double Area()
    {
        return Width * Height;
    }
}

namespace PolymorphismTest
{
    class Program
    {
        static void Main(string[] args)
        {
            TwoDShape[] shapes = new TwoDShape[4];
            shapes[0] = new Triangle("right", 8.0, 12.0);
            shapes[1] = new Rectangle(10);
            shapes[2] = new Rectangle(10, 4);
            shapes[3] = new Triangle(7.0);
            for (int i = 0; i < shapes.Length; i++)
            {
                Console.WriteLine("object is " + shapes[i].name);
                Console.WriteLine("Area is " + shapes[i].Area());
                Console.WriteLine();
            }

        }
    }
}
*/

