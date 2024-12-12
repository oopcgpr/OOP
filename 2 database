// Database


#include <iostream>
#include <cstring>
using namespace std;

class person_additional_info
{
	char address[20], license[20], insurance[20];
	long int contact;

public:
	person_additional_info()
	{
		strcpy(address, "xyz");
		strcpy(license, "xy-0000");
		strcpy(insurance, "xy000");
		contact = 0000;
	}
	~person_additional_info()
	{
		cout << "i am in destructor\n";
	}
	friend class person;
};

class person
{
	char name[20], dob[10], blood[10];
	float ht, wt;
	static int count;
	person_additional_info *pai;

public:
	person()
	{
		strcpy(name, "xyz");
		strcpy(dob, "dd/mm/yy");
		strcpy(blood, "A+");
		ht = 0;
		wt = 0;
		pai = new person_additional_info();
	}
	person(person *p1)
	{
		strcpy(name, p1->name);
		strcpy(dob, p1->dob);
		strcpy(blood, p1->blood);
		ht = p1->ht;
		wt = p1->wt;
		pai = new person_additional_info();
		strcpy(pai->address, p1->pai->address);
		strcpy(pai->license, p1->pai->license);
		strcpy(pai->insurance, p1->pai->insurance);
		pai->contact = p1->pai->contact;
	}
	static void showcase()
	{
		cout << "\n no of records count=" << count << "\n";
	}
	~person()
	{
		cout << "\n i am in destructor\n";
		delete pai;
	}
	void getdata(char name[20]);
	inline void display();
};

int person::count = 0; // Static variable initialization

void person::getdata(char name[20])
{
	strcpy(this->name, name);
	cout << "\n enter date of birth: ";
	cin >> dob;
	cout << "\n enter blood group: ";
	cin >> blood;
	cout << "\n enter height: ";
	cin >> ht;
	cout << "\n enter weight: ";
	cin >> wt;
	cout << "\n enter address: ";
	cin >> pai->address;
	cout << "\n enter license no: ";
	cin >> pai->license;
	cout << "\n enter insurance policy no: ";
	cin >> pai->insurance;
	cout << "\n enter contact no: ";
	cin >> pai->contact;
	count++;
}

void person::display()
{
	cout << "\t" << name;
	cout << "\t" << dob;
	cout << "\t" << blood;
	cout << "\t" << ht;
	cout << "\t" << wt;
	cout << "\t" << pai->address;
	cout << "\t" << pai->license;
	cout << "\t" << pai->insurance;
	cout << "\t" << pai->contact;
}

int main()
{
	person *p1, *p2;
	int ch;

	p1 = new person;
	p2 = new person(p1);

	cout << "\t name";
	cout << "\t dob";
	cout << "\t blood";
	cout << "\t ht";
	cout << "\t wt";
	cout << "\t address";
	cout << "\t license";
	cout << "\t insurance";
	cout << "\t contact";
	cout << endl;

	cout << "Default constructor value\n";
	p1->display();
	cout << "\n";

	cout << "Copy constructor value\n";
	p2->display();

	int n;
	cout << "\n Enter how many records you want: ";
	cin >> n;

	person p3[n];
	char name[20];
	int x = 0;

	do
	{
		cout << "\n Welcome to personal database system";
		cout << "\n1. Enter the record";
		cout << "\n2. Display the record";
		cout << "\n3. Exit";
		cin >> ch;

		switch (ch)
		{
		case 1:
		{
			cout << "\n Enter the name: ";
			cin >> name;
			p3[x].getdata(name);
			person::showcase();
			x++;
			break;
		}
		case 2:
		{
			cout << "\t name";
			cout << "\t dob";
			cout << "\t blood";
			cout << "\t ht";
			cout << "\t wt";
			cout << "\t address";
			cout << "\t license";
			cout << "\t insurance";
			cout << "\t contact";
			for (int i = 0; i < n; i++)
			{
				cout << "\n";
				p3[i].display();
			}
			break;
		}
		case 3:
			cout << "Exiting...\n";
			break;
		default:
			cout << "Invalid choice, try again.\n";
		}
	} while (ch != 3);

	delete p1;
	delete p2;

	return 0;
}

