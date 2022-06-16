#include <iostream>
using namespace std;
int main()
{
    srand(time(NULL));
    const int size = 10;
    int arr[size];
    for (int i = 0; i < size; i++)
    {
        arr[i] = rand() % 100;
    }

    for (int i = 0; i < size; i++)
        cout << arr[i] << ", ";
    cout << endl <<"Sorted array:";

    int index, temp;
    for (int i = 0; i < (size - 1); i++) {
        index = i;
        temp = arr[i];
        for (int j = i + 1; j < size; j++)
            if (arr[j] < temp) {
                temp = arr[j];
                index = j;
            }
        swap(arr[i], arr[index]);
    }

    for (int i = 0; i < size; i++)
        cout << arr[i] << ", ";
}
