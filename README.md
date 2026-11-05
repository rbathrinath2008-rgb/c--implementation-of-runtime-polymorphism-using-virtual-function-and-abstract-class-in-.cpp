# c--implementation-of-runtime-polymorphism-using-virtual-function-and-abstract-class-in-.cpp
c++-implementation of runtime polymorphism using virtual function and abstract class in .cpp
#include<iostream>
using namespace std;

class shape{
    public:
        virtual float area()=0;
        virtual ~shape() {}
};

class circle:public shape{
    private:
        float radius;
    public:
        circle(float r){
            radius=r;
        }
        float area(){
            return 3.14*radius*radius;
        }
};

class rectangle:public shape{
    private:
        float length;
        float breadth;
    public:
        rectangle(float l,float b){
            length=l;
            breadth=b;
        }
        float area(){
            return length*breadth;
        }
};

class triangle:public shape{
    private:
        float base;
        float height;
    public:
        triangle(float b,float h){
            base=b;
            height=h;
        }
        float area(){
            return 0.5*base*height;
        }
};

int main(){
    float r, l, b, base, h;

    cout<<"Enter radius of circle: ";
    cin>>r;

    cout<<"Enter length and breadth of rectangle: ";
    cin>>l>>b;

    cout<<"Enter base and height of triangle: ";
    cin>>base>>h;

    circle c(r);
    rectangle rect(l,b);
    triangle t(base,h);

    shape *ptr;

    ptr = &c;
    cout<<"area of circle: "<<ptr->area()<<endl;

    ptr = &rect;
    cout<<"area of rectangle: "<<ptr->area()<<endl;

    ptr = &t;
    cout<<"area of triangle: "<<ptr->area()<<endl;

    return 0;
}
