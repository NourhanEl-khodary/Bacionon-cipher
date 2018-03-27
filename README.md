# Bacionon-cipher
ciphering and deciphering mesages
#include "stdafx.h"
#include <iostream>
#include <string>

using namespace std;


int main()
{
	char cipher[101];
	char alphapet[26] = { 'a','b','c','d','e','f','g','h','i','j','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z' };
	char Alphapet[26] = { 'A','B','C','D','E','F','G','H','I','J','K','L','M','N','O','P','Q','R','S','T','U','V','W','X','Y','Z' };
	string ciphered[26] = { "aaaaa","aaaab","aaaba","aaabb","aabaa","aabab","aabba","aabbb","abaaa","abaab","ababa","ababb","abbaa","abbab","abbba","abbbb","baaaa","baaab","baaba","baabb","babaa","babab","babba","babbb","bbaaa","bbaab" };
	int option;
	string coded;
	char dicipher[501];
	string diciphered;
	char result;
	cout << "Welcome User!" << endl;
	cout << "1- Cipher " << endl << "2- Decipher" << endl << "3- End" << endl << "Choose an Option by Entering the Number: ";
	cin >> option;
	if (option == 1) {
		cout << "Enter the Messeage You Want to Cipher .....  " << endl;
		cin.ignore();
		cin.getline(cipher, 100,'\n');
		cout << endl;
		cout << "The Ciphered Message is " << endl;
		for (int i = 0; i < (strlen(cipher)); i++) {
			for (int j = 0; j < 26; j++) {
				if (cipher[i] == ' ') {
					cout << ' ';
					break;
				}
				else if ((cipher[i] == alphapet[j]) || (cipher[i] == Alphapet[j])) {
					coded = ciphered[j];
					cout << coded;
				}
			}
			cout << ' ';
		}
		cout << endl;
	}
	

	else if (option == 2) {
		cout << "Enter the Messeage You Want to Dicipher .....  " << endl;
		cin.ignore();
		cin.getline(dicipher, 500, '\n');
		cout << endl;
		for (int i = 0; i < strlen(dicipher); i++) {	
			if (dicipher[i] == ' ') {
				diciphered += dicipher[i - 5];
				diciphered += dicipher[i - 4];
				diciphered += dicipher[i - 3];
				diciphered += dicipher[i - 2];
				diciphered += dicipher[i - 1];
				for (int j = 0; j < 26; j++) {
					if (diciphered == ciphered[j]) {
						result = alphapet[j];
						cout << result;
					}
				}
			}
			if ((dicipher[i] == ' ') && (dicipher[i + 1] == ' ')) {
				cout << ' ';
			}
			diciphered.clear();
		}
		cout << endl;
	}
	else if (option == 3) {
		return 0;
	}
    return 0;
}
