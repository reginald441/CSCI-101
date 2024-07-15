/*
 * Program Name: Triangle Summarizing
 * Author: Reginald Kargbo
 * Date Last Updated: 2/4/23
 * Purpose: Enter the lengths of a triangle and determine its validity and type.
 */

#include <iostream>
#include <cmath>

using namespace std;

bool isValidTriangle(float side1, float side2, float side3) {
    return (side1 + side2 > side3) && (side1 + side3 > side2) && (side2 + side3 > side1);
}

bool isRightTriangle(float side1, float side2, float side3) {
    return (pow(side1, 2) + pow(side2, 2) == pow(side3, 2)) ||
           (pow(side1, 2) + pow(side3, 2) == pow(side2, 2)) ||
           (pow(side2, 2) + pow(side3, 2) == pow(side1, 2));
}

int main() {
    float side1, side2, side3;

    cout << "Enter the lengths of the three sides of the triangle: ";
    cin >> side1 >> side2 >> side3;

    if (!cin) {
        cerr << "Invalid input. Please enter numeric values." << endl;
        return 1;
    }

    if (isValidTriangle(side1, side2, side3)) {
        cout << "You have a valid triangle." << endl;

        if (isRightTriangle(side1, side2, side3)) {
            cout << "And it is a right triangle." << endl;
        }
    } else {
        cout << "The lengths do not form a triangle." << endl;
    }

    return 0;
}
