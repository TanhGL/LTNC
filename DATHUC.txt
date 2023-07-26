#include <iostream>

using namespace std;

class BacNhat {
	int a, b;
public:
	BacNhat(int _a = 0, int _b = 0) {
		a = _a;
		b = _b;
	}
	BacNhat(const BacNhat& bn) {
		a = bn.a;
		b = bn.b;
	}
	~BacNhat() {};
	friend istream& operator >> (istream& is, BacNhat& bn) {
		is >> bn.a >> bn.b;
		return is;
	}
	friend ostream& operator << (ostream& os, BacNhat& bn) {
		if (bn.b > 0) {
			os << bn.a << "x+" << bn.b;
		}
		else {
			os << bn.a << "x" << bn.b;
		}
		return os;
	}
	int tinh(int x) {
		return a * x + b;
	}
	BacNhat operator + (BacNhat& bn) {
		BacNhat kq;
		kq.a = a + bn.a;
		kq.b = b + bn.b;
		return kq;
	}
	bool operator == (BacNhat& bn) {
		if (a + b == bn.a + bn.b) {
			return true;
		}
		return false;
	}
};

int main() {
	BacNhat a, b;
	cin >> a >> b;
	int x;
	cin >> x;
	cout << a << endl;
	cout << b << endl;
	BacNhat c = a + b;
	cout << a << "+" << b << "=" << c << endl;
	cout << a.tinh(x) << endl;
	cout << b.tinh(x) << endl;
	if (a == b) {
		cout << "TRUE" << endl;
	}
	else {
		cout << "FALSE" << endl;
	}
	return 0;
}