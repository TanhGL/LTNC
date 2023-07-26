#include <iostream>
#include <fstream>
#include <cmath>
using namespace std;

bool kiemtra(int n) {
	int x = sqrt(n);
	if (x * x == n) {
		return true;
	}
	else {
		return false;
	}
}

int main() {
	ifstream ifile("FSTREAM.inp");
	ofstream ofile("FSTREAM.out");
	int n;
	ifile >> n;
	if (kiemtra(n) == true) {
		ofile << "YES";
	}
	else {
		ofile << "NO";
	}

	ifile.close();
	ofile.close();
	return 0;
}