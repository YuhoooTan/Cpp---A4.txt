#include <iostream>
#include <fstream>
using namespace std;

int main() {

    ofstream out("color.txt");

    if (out.is_open()) {
        out << "Red\n";
        out << "Blue\n";
        out << "Green\n";
        out << "Yellow\n";
        out << "Purple\n";
        out.close();
    } else {
        cout << "Error creating file!" << endl;
        return 1;
    }

   
    ifstream in("color.txt");
    ofstream copy("color_copy.txt");

    if (in.is_open() && copy.is_open()) {
        string line;

        while (getline(in, line)) {
            copy << line << endl;
        }

        in.close();
        copy.close();

        cout << "Copy successful!" << endl;
    } else {
        cout << "Error opening file!" << endl;
    }
    

    return 0;
}
