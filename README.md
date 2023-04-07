# H-t.-08-04-2023
//---------------------------------------------
#include<iostream>
#include <iomanip>
#include <string>
using namespace std;

class House
{
public:
    int ch; 
    int n;
    void NumFlats()
    {
        cout << "Введите количество этажей в доме - ";
        cin >> n;
        cout << "Количество квартир - " << ch << endl;
        int** arr = new int* [n];
        for (int i = 0; i < n; i++)
        {
            arr[i] = new int[ch];
            for (int j = 0; j < ch; j++)
            {
                arr[i][j] = 1; 
                cout << "|";
                cout << arr[i][j] << '|';
            }
            cout << endl;
        };
        for (int i = 0; i < n; i++)
        {
            delete[] arr[i];
            delete arr[n];
        };
    }
};

class Flats
{
public:
    int a;
    int s = 0;
    int* residents = new int[a];
    void PRint()
    {
        for (int i = 0; i < a; i++)
        {
            residents[i] = i;
            s = s + 1;
        }
        cout << "Количество жильцов - " << s << endl;
        cout << endl;
    }
};

class Residents
{
public:
    char name[10];
    char surname [15];
    int kod;
    void get();
    void put();
};

void Residents::get()
{
    cout << "Введите код от домофона - ";
    cin >> kod;
    cout << "Введите имя жильца - ";
    cin >> name;
    cout << "Введите фамилию жильца - ";
    cin >> surname;
}

void Residents::put()
{
    cout << "Код: " << kod << endl;
    cout << "Имя жильца: " << name << endl;
    cout << "Фамилия жильца: " << surname << endl;
}

int main()
{
    Residents people[30];
    House home;
    Flats flat;
    int i;
    cout << "Количество жильцов в доме - ";
    cin >> home.ch;
    cout << endl;
    flat.a = home.ch;
    for (i = 0; i < home.ch; i++)
    {
        people[i].get();
    }
    cout << "\nДанные о жильцах - " << endl;
    for (i = 0; i < home.ch; i++)
    {
        people[i].put();
    }
    flat.PRint();
    cout << "----------" << endl;
    cout << "Вам педоставляется планировка дома: \n";
    cout << endl;
    home.NumFlats();
    return 0;
}
//---------------------------------------------
