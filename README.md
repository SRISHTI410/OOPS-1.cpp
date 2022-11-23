# OOPS-1.cpp

#include <iostream>
#include <fstream>
#include <iomanip>
using namespace std;
	void book(int x)
		{
				try
				{
				    if(x>100)
				  
				        throw x;
				}
				    catch(int x)
				    {
				        cout<<"exception caught.";
				    }
				}



class ride{
	public:
		string name,add;
		int age;
		char a[60];
		virtual void book()      //virtual function//
		{
			cout<<"enter name: "<<endl;
			cin>>name;
			cout<<"enter age: "<<endl;
			cin>>age;
			cout<<"enter address: "<<endl;
			cin>>add;
		} 
};
class bike
{
	public:
		int ch,price;
		void book()
		{
			cout<<"Bike service is upto 30 kms.";
			cout<<"Enter the distance: "; 
				cin>>ch;
				if(1<ch<10)
				{

					price=90;
					cout<<"\nYou have booked mini bike"<<endl; 
				}
				else if (11<=ch<=30)
				{
				price=140;
					cout<<"\nYou have booked yamaha bike"<<endl; 
				}
				else
				{
				    cout<<"Opt for Car service.";
				}
		}		
};
class car:public ride
{
    	public:
		int ch1,p1;
		void book()
		{
			cout<<"Car service.";
			cout<<"Enter the distance: "; 
				cin>>ch1;
				if(31<=ch1<=50)
				{

					p1=290;
					cout<<"\nYou have booked mini car"<<endl; }
				else if (51<=ch1<=100)
				{
				p1=840;
					cout<<"\nYou have booked sedan"<<endl; 
				}
		}
	
};

class receipt: public bike,public car
{
	public:
		void bill()
		{
			ofstream outf;
			outf.open("C:\\Users\\KIIT\\OneDrive\\Documents\\records.txt");
			
			{
				outf<<"receipt"<<endl;
				outf<<"customer Name"<<name<<endl;

				if(1<=ch<=10){
					price=40;
				}
				else if (11<=ch<=30)
				{
				price=140;
				}
				if(31<=ch1<=50)
				{

					price=290;
				}
				else if (51<=ch1<=100)
				{
				price=840;
					
				}

				outf<<"price: "<<price<<endl;

			}
			outf.close();
		}
		void display(){
			ifstream ifs("records.txt");
			{
				if(!ifs)
				{
					cout<<"file error"<<endl;
				}
				while(!ifs.eof())
				{
					ifs.getline(a,60);
				}
			}
			ifs.close();
		}
};


int main()
{
    book(101);
	int c,back;
	int a;
do
	{
	cout<<"\t press 1 to add details "<<endl;
	cout<<"\t press 2 to book bike"<<endl;
		cout<<"\t press 3 to book car"<<endl;
	cout<<"\t press 4 for receipt"<<endl;
	cout<<"\t press 5 to exit "<<endl;
	cout<<"enter the choice"<<endl;
	cin>>c;
	ride *r; 
	bike b;
		car sed;
	receipt n;

	switch(c)
	{

		case 1:
			
			 
				cout<<"customers"<<endl;
				r->book();
				break;
			
		case 2:
			
			    
				cout<<"bookings using bike:"<<endl;
				b.book();
				break;
			
			case 3:
			
			   r = &sed;
				cout<<"bookings using car:"<<endl;
				r->book();
				break;
			
		case 4:
			
				n.bill();
				cout<<"press 1 to display your ticket";
				cin>>back;

				if(back==1){
				n.display();
					
			break;
				}
			
		case 5:
			{
				cout<<"thank you"<<endl;
				break;
			}
			default:
			{
				cout<<"invalid input please try again"<<endl;
				break;
			}
	
} 
}while(a--);
	return 0;
}
