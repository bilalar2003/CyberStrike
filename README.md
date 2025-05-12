#include <iostream>
#include <string>
#include <cstring>
using namespace std;

void SecondFullStop()
{
	string str;
	char* substr = NULL;
	int i, idx = 0, fstops = 0;

	cout << "Enter your string: ";
	getline(cin, str);

	for (i = str.size() - 1; i >= 0; i--) {
		if (str[i] == '.')
			fstops++;
		else if (fstops == 2) {
			idx = i;
			break;
		}
	}

	if (fstops < 2)
		cout << "Error, string containing less than 2 fullstops." << endl;
	else {
		substr = new char[idx + 1];
		for (i = 0; i <= idx; i++)
			substr[i] = str[i];
		cout << substr;
	}
}