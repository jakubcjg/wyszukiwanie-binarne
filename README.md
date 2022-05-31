#include <iostream>
using namespace std;

int BinSearch(int search)
{
	
	int tab[15] = { 2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37, 41, 43, 47 };

	int l = 0;
	int p = 15;
	int Mid = (l + p) / 2;

	while (l <= p) 
	{
		if (tab[Mid] == search) {
			return Mid;
		}
		else if (tab[Mid] > search) {
			p = Mid - 1;
		}
		else if (tab[Mid] < search) {
			l = Mid + 1;
		}

		Mid = (l + p) / 2;
	}

	return -1;
}

int main() 
{
	int numSearch, numPosition;

	cout << "Podaj liczbe ktora chcesz znalezc: ";
	cin >> numSearch;

	numPosition = BinSearch(numSearch);
	cout << "Liczba " << numSearch << " wystepuje w zbiorze w komorce o indeksie " << numPosition;
}
