#include <iostream>
#include <ctime>
#include <cmath>

using namespace std;

int main()
{
    int xi, yi, p, rad = 0;
    double score = 0;

    srand(time(NULL));

    for (int i = 1; i <= 5; i++)
    {
        cout << "Enter the coordinates xi and yi for shot number "<< i << endl;
        cin >> xi >> yi;

        xi += rand() % 10 - 5;
        yi += rand() % 10 -5;
        rad = sqrt(pow(xi, 2) + pow(yi, 2));
        p = 5 - rad;

        if ((p & (1 << 31))){
            p = 0;
        }
        score += p;
    }

    cout << "Your score " << score << endl;
    if (score > 10)
    {
        cout << "You win!" << endl;
    }
    else
    {
        cout << "Loser!!!" << endl;
    }
    return 0;
}
