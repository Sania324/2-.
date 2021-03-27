//3 вариант. "Студент":
//фамилия.имя.отчество.пол.национальность.рост.вес.дата рождения.(год,месяц,число). номер телефона. домашний адрес.(поштовий 
//индекс,область,район,город,улица,дом,квартира)ВУЗ,Курс,группа,средний бал,специальность.
#include <iostream>
#include <string>
#include <stdlib.h>
using namespace std;



struct Student {
    string FirstName, SecondName, LastName;
    string Sex;
    string Nationality;
    int height;
    int weight;
    string BirthdayDate[3];//Year,month,number
    char PhoneNumber[20];
    string HomeAdress[8];//Post index,Country,region,district, city, street, house, apartment
    string Universety[4];//course, group, grade point average, specialty

};

Student InitStudent();
Student* InitArray(int);
void DisplayArray(Student*, int);
void DisplayStudent(Student);

int main() {
    int Dimension;
    cout << "Enter the number of people you want to create" << endl;
    cin >> Dimension;
    Student* MassiveStruct;
    MassiveStruct = InitArray(Dimension);
    DisplayArray(MassiveStruct, Dimension);

}
Student InitStudent() {
    Student Man;
    cout << "Enter first name:" << endl;
    cin >> Man.FirstName;
    cout << "Enter second name:" << endl;
    cin >> Man.SecondName;
    cout << "Enter last name:" << endl;
    cin >> Man.LastName;
    cout << "Enter sex:" << endl;
    cin >> Man.Sex;
    cout << "Enter Nationality:" << endl;
    cin >> Man.Nationality;
    cout << "Enter number of height:" << endl;
    cin >> Man.height;
    cout << "Enter number of weight:" << endl;
    cin >> Man.weight;
    cout << "Enter number  year of birthday:" << endl;
    cin >> Man.BirthdayDate[0];
    cout << "Enter number  month of birthday:" << endl;
    cin >> Man.BirthdayDate[1];
    cout << "Enter number of birthday:" << endl;
    cin >> Man.BirthdayDate[2];
    cout << "Enter phone number :" << endl;
    cin >> Man.PhoneNumber;
    cout << "Enter post index:" << endl;
    cin >> Man.HomeAdress[0];
    cout << "Enter country:" << endl;
    cin >> Man.HomeAdress[1];
    cout << "Enter region:" << endl;
    cin >> Man.HomeAdress[2];
    cout << "Enter district:" << endl;
    cin >> Man.HomeAdress[3];
    cout << "Enter city:" << endl;
    cin >> Man.HomeAdress[4];
    cout << "Enter streat:" << endl;
    cin >> Man.HomeAdress[5];
    cout << "Enter house:" << endl;
    cin >> Man.HomeAdress[6];
    cout << "Enter number of apartments:" << endl;
    cin >> Man.HomeAdress[7];
    cout << "Enter  number of your course" << endl;
    cin >> Man.Universety[0];
    cout << "Enter  your group" << endl;
    cin >> Man.Universety[1];
    cout << "Enter  number of your  grade point average" << endl;
    cin >> Man.Universety[2];
    cout << "Enter  number of your  speciality" << endl;
    cin >> Man.Universety[3];
    return Man;
}
Student* InitArray(int Dimension) {
    Student* Massive = new Student[Dimension];
    for (int i = 0; i < Dimension; i++) {
        cout << "Enter the information about " << i << " person" << endl;
        Massive[i] = InitStudent();

    }

    return Massive;
}
void DisplayArray(Student* Massive, int Dimension) {
    for (int i = 0; i < Dimension; i++) {
        DisplayStudent(Massive[i]);
    }
}
void DisplayStudent(Student Man) {
    cout << Man.FirstName << " " << Man.SecondName << " " << Man.LastName << endl;
    cout << "Sex:" << Man.Sex << "  " << "Nationality:" << Man.Nationality << "  " << "Height:" << Man.height << "  " << "Weight:" << Man.weight << endl;
    //Output BirthdayDate[3]
    cout << "Birthday date: year{" << Man.BirthdayDate[0] << "},month{" << Man.BirthdayDate[1] << "},day{" << Man.BirthdayDate[2] << "}" << endl;
    cout << "Phone number:";
    for (int i = 0; i < 20; i++) {
        if (Man.PhoneNumber[i + 1] == NULL) {
            cout << Man.PhoneNumber[i];
            break;
        }
        cout << Man.PhoneNumber[i];
    }
    cout << endl;
    //output  HomeAdress[8]
    cout << "Post index: " << Man.HomeAdress[0] << ", Country: " << Man.HomeAdress[1] << ", Region: " << Man.HomeAdress[2] << ", District: " << Man.HomeAdress[3] << ", City: " << Man.HomeAdress[4] << ", Street: " << Man.HomeAdress[5] << ", House: " << Man.HomeAdress[6] << ", Number of apartment: " << Man.HomeAdress[7] << endl;
    //output Universety[4]
    cout << "Number of course: " << Man.Universety[0] << ", Group: " << Man.Universety[1] << ", Grade point average: " << Man.Universety[2] << ", Speciality: " << Man.Universety[3] << endl;
}
