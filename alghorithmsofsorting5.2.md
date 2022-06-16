#include <string>
#include <cstring>
#include <iostream>
using namespace std;
const int maxsize = 15;
void coding(char* arr)
{
    for (int i = 0; i < maxsize; i++)
    {
        int sa;
        sa = rand() % 100;
        if (sa <= 15)arr[i] = 'a';
        else
        {
            if (sa <= 18)arr[i] = 'b';
            else
            {
                if (sa <= 68)arr[i] = 'c';
                else
                {
                    if (sa <= 93)arr[i] = 'd';
                    else
                    {
                        if (sa <= 100)arr[i] = 'e';
                    }
                }
            }
        }
        cout << " " << arr[i] << "  ";
    }
    cout << endl;
    for (int i = 0; i < maxsize; i++)
    {
        if (arr[i] == 'a')cout << "001 ";
        if (arr[i] == 'b')cout << "10  ";
        if (arr[i] == 'c')cout << "11  ";
        if (arr[i] == 'd')cout << "000 ";
        if (arr[i] == 'e')cout << "01  ";
        if (i == maxsize - 1)
        {
            cout << endl << endl;
        }
    }
}
void decoding()
{
    int c = 5;
    char arr2[3];
        while (c != 0)
        {
            cout << "Type binary number that should be decoded(a - 001, b - 10, c-11, d-000, e-01: " << endl;
            cin >> arr2;
            if (arr2[0] == '0' && arr2[1] == '0' && arr2[2] == '1')cout << "a ";
            else if (arr2[0] == '1' && arr2[1] == '0')cout << "b ";
            else if (arr2[0] == '1' && arr2[1] == '1')cout << "c ";
            else if (arr2[0] == '0' && arr2[1] == '0' && arr2[2] == '0')cout << "d ";
            else if (arr2[0] == '0' && arr2[1] == '1')cout << "e ";
            else
            {
                cout << "Binary number is wrong" << endl;
            }
            cout << endl;
            cout << "0 - Exit. Any number - Continue" << endl;
            cin >> c;
            if (c == 0) system("pause");
        }
}
int main()
{
    srand(time(NULL));
    char* arr = new char[maxsize];
    coding(arr);
    decoding();
}
