# Array-Backwards

 

#include <iostream>
#include <climits>

using namespace std;

int main() {

 

    // Data Abstraction:
    const int MAX_CAPACITY = 100;
    int MAX_NUMBERS; 
    
    int userNumbers[MAX_CAPACITY];
    int reverseNumbers[MAX_CAPACITY];
    
    int max = INT_MIN;
    int min = INT_MAX;
    int num;
    int sum = 0;
    int duplicates = 0;

 

    // Input:
    cout << "Input the number of elements to store in the array: ";
    cin >> MAX_NUMBERS;
    cout << MAX_NUMBERS << endl;
    
    cout << "Input " << MAX_NUMBERS << " integers : " << endl;
    for (int i = 0; i < MAX_NUMBERS; ++i){
        cin >> num;
        userNumbers[i] = num;
    }
    

 

    // Process:
     for (int i = 0; i < MAX_NUMBERS; ++i){
        //PRINT INTEGER W/ CORRESPNDING ELEMENT
        cout << "integer - " << i << ": " << userNumbers[i] << endl;
        //SUM
        sum = sum + userNumbers[i];
        //MINIMUM AND MAXIMUM
        if (userNumbers[i] > max){
            max = userNumbers[i];
        }
        if (userNumbers[i] < min){
            min = userNumbers[i];
        }
    }
    //FINDING DUPLICATES
    for (int i = 0; i < MAX_NUMBERS; ++i) {
        bool alreadyCounted = false;
        bool foundDuplicateLater = false;
 
        for (int j = 0; j < i; ++j) {
            if (userNumbers[i] == userNumbers[j]) {
                alreadyCounted = true;
            }
        }
        if (!alreadyCounted) {
            for (int j = i + 1; j < MAX_NUMBERS; ++j) {
                if (userNumbers[i] == userNumbers[j] && !foundDuplicateLater) {
                    duplicates++;
                    foundDuplicateLater = true;
                }
            }
        }
    }
    
    for (int i = 0; i < MAX_NUMBERS; ++i){
        reverseNumbers[i] = userNumbers[(MAX_NUMBERS - 1) - i];
    }

    // Output:
    cout << endl;
    
    cout << "The values stored into the array are : " << endl;
    for (int i = 0; i < MAX_NUMBERS; ++i){
        cout << userNumbers[i] << " ";
    }
    
    cout << endl;
    cout << endl;
    
    cout << "The values stored into the array in reverse are : " << endl;
    for (int i = 0; i < MAX_NUMBERS; ++i){
        cout << reverseNumbers[i] << " ";
    }
    
    cout << endl;
    cout << endl;
    
    cout << "The sum of all elements of the array is ";
    cout << sum << endl;
    cout << "The total number of duplicate elements in the array is ";
    cout << duplicates << endl;
    cout << "The maximum and minimum element in the array are ";
    cout << max << " , " << min << endl;
 

    // Assumptions:

 

    

 

    return 0;

 

}
