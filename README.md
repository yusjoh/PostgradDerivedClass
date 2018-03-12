#ifndef POSTGRADSTD_H
#define POSTGRADSTD_H

#include <iostream>
#include "Student.h"
#include <string>

using namespace std;


class PostgradStd: public Student
{
public:
    PostgradStd();
    PostgradStd(string ndissertation);
    string get_dissertation();
    string get_degree();
    void set_Degree(string new_degree);
    void set_dissertation(string new_dissertation);
    void display_info();
    int calcFee();

private:
    string dissertation;
};

#endif // POSTGRADSTD_H

#include "PostgradStd.h"

#include <iostream>

PostgradStd::PostgradStd()
{
    dissertation = " ";
}
PostgradStd::PostgradStd(string ndissertation)
{
    dissertation = ndissertation;
}
string PostgradStd::get_dissertation()
{
    return get_dissertation();
}
void PostgradStd::set_dissertation(string new_dissertation)
{
    dissertation = new_dissertation;
}
void PostgradStd::display_info()
{
    cout << "Name: " << get_name() << endl;
    cout << "Student Number: " << get_number() << endl;
    cout << "Address: " << get_address() << endl;
    cout << "degree: " << get_degree() << endl;
    cout << "Dissertation" << get_dissertation() << endl;

}
string PostgradStd::get_degree()
{
    return stDegree;
}
void PostgradStd::set_Degree(string newDegree)
{
    stDegree = newDegree;
}
int PostgradStd::calcFee()
{
    char degreeChar;
    degreeChar = get_degree()[0];
    int underGradFee = 500;
    int postGradFee = 1200;

    switch(degreeChar)
    {
    case 'p':
    case 'P': return postGradFee;
    default: return underGradFee;
    }

}

