# Oblique-Triangle-AAS-Calculator-
Assignment for the CPE112L(SC:786);Programming Logic &amp; Design
#include <iostream>
#include <math.h>
#define pi 3.14159265358989

using namespace std;
double A = 0;
double a = 0;
double B = 0;
double b = 0;
double C = 0;
double c = 0;
double x,y;

void degrad();//Converts Degrees to Radians
void missang();//Finds the missing angle if two are known in a triangle
void angcheck();//Checks for an angle >180
void line();// a line

int main()
{
  cout << "Give each angle:\n";
  cout << "m<A = "; cin >> A;
  cout << "m<B = "; cin >> B;
  cout << "m<C = "; cin >> C;
  angcheck();
  missang();
  line();

  cout << "Solution for each angle:" << endl << endl;
  cout << "m<A = " << A << endl;
  cout << "m<B = " << B << endl;
  cout << "m<C = " << C << endl;
  line();

  cout << "Give each side:\n" << endl;
  cout << "a = "; cin >> a;
  cout << "b = "; cin >> b;
  cout << "c = "; cin >> c;
  angcheck();
  degrad();

  //formula of each side
  a = (b*sin(A)/sin(B));
  b = (a*sin(B)/sin(A));
  c = (b*sin(C)/sin(B));
  line();

  cout << "The Solution of the side triangle is:" << endl << endl;
  cout << "a = " << a << endl;
  cout << "b = " << b << endl;
  cout << "c = " << c << endl;
  line();
  cout << "Mollweide's Equation:"<< endl << endl;
  x = (a-b)/c;
  y= sin((A-B)/2)/cos(C/2);
  printf("%f is equal to %f",x,y);

  return 0;
}
void angcheck()
{
  if (A >= 180 || B >= 180 || C >= 180)
  {
  cout << "Error, one or more angle(s) is/are too large. Please try again." << endl;
  }
}
void degrad()
{
  //Converts degrees to radians
  A = A * (pi / 180);
  B = B * (pi / 180);
  C = C * (pi / 180);
}
void missang()
//Finds the missing angle if only 2 are entered
{
  if (A == 0 && B != 0 && C != 0)
  {
    A = 180 - C - B;
  }
  else if (A != 0 && B == 0 && C !=0)
  {
    B = 180 - A - C;
  }
  else if (A != 0 && B != 0 && C == 0)
  {
    C = 180 - A - B;
  }

}
void line()
{
  cout << "------------------------------------" << endl;
}
