#include <fstream>
#include <iostream>
#include <string.h>

using namespace std;

struct BAGS

{

    char title[20];

    char country[20];

    int year;

    int previews;

    int price;

};

BAGS bg;

char path[] = "bags.txt";

int main()

{

    fstream f;

    int x, y;

    char tit[20];

    int flag = 0;
    //const int ADD_NEW_BAG = 1;
    //const int MENU_SEARCH_BY_BRAND = 2;
    //const int SEARCH_BY_YEAR = 3;
    //const int LIST = 4;
    //const int EXIT = 0;
    cout << "\tBAGS (LINEAR PROGRAM)" << endl;
    do

    {


        cout << "1 - Add a new bag" << endl;

        cout << "2 - Search by brand" << endl;

        cout << "3 - Search by year" << endl;

        cout << "4 - List of bag" << endl;

        cout << "0 - Exit" << endl;


        cin >> x;

        switch (x)

        {

        case 1:

        {

            f.open(path, ios_base::app);

            if (!f)

            {

                cout << "error";

            }

            else

            {

                cout << "Brand of bag: ";

                fflush(stdin);

                gets(bg.title);

                cout << "Country of origin: ";

                cin >> bg.country;

                cout << "Year: ";

                cin >> bg.year;

                cout << "Good previews(in percentages): ";

                cin >> bg.previews;

                cout << "Price: ";

                cin >> bg.price;

                f.write((char*)&bg, sizeof(BAGS));

                f.close();

            }

        }
        break;

        case 2:

        {

            f.open(path, ios_base::in);

            if (!f)

            {

                cout << "error";

            }

            else

            {

                cout << "Brand: ";

                fflush(stdin);

                gets(tit);
                while ((f.read((char*)&bg, sizeof(BAGS))))

                {

                    if (strcmp(tit, bg.title) == 0)

                    {

                        flag = 1;

                        cout << x << endl;

                        cout << "Brand: " << bg.title << endl;

                        cout << "Country of origin: " << bg.country << endl;

                        cout << "Year: " << bg.year << endl;

                        cout << "Good previews(in percentages): " << bg.previews << endl;

                        cout << "Price: " << bg.price << endl;

                    }

                }

                f.close();

                if (!flag)

                    cout << "Repeat please, this bag isn't in list\n";

            }

        }
        break;

        case 3:

        {

            f.open(path, ios_base::in);

            if (!f)

            {

                cout << "error";

            }

            else

            {

                cout << "Year: ";

                cin >> y;

                while ((f.read((char*)&bg, sizeof(BAGS))))

                {

                    if (bg.year >= y)

                    {

                        cout << "Brand: " << bg.title << endl;

                        cout << "Country of origin: " << bg.country << endl;

                        cout << "Year: " <<bg.year << endl;

                        cout << "Good previews(in percentages): " << bg.previews << endl;

                        cout << "Price: " << bg.price << endl;

                        cout << "===============================\n";

                    }

                }

            }

            f.close();

        }
        break;

        case 4:

        {

            f.open(path, ios_base::in);

            if (!f)

            {

                cout << "error" << endl;

            }

            else

            {

                while ((f.read((char*)&bg, sizeof(BAGS))))

                {

                        cout << "Brand: " << bg.title << endl;

                        cout << "Country of origin: " <<bg.country << endl;

                        cout << "Year: " << bg.year << endl;

                        cout << "Good previews(in percentages): " << bg.previews << endl;

                        cout << "Price: " << bg.price << endl;

                        cout << "===============================\n";

                }

            }

            f.close();

        }

        }

    }
    while (x != 0);

    return 0;

}
