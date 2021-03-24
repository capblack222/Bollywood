//this is a game called BOLLYWOOD
#include<iostream.h>
#include<fstream.h>
#include<conio.h>
#include<string.h>
#include<stdio.h>
#include<stdlib.h>
#include<dos.h>
#include<ctype.h>

//using namespace std;

class player
{

 char name[20];
 int sc;
 int timesplayed;

 public:
 player()
 {
 timesplayed=1;
 sc=0;
 }
 void getdata()
 {
	 cout<<"Enter your name:";
	 cin>>name;
 }

 char * getname()
 {
	 return name;
 }

 void score(int chance)
 {
	 sc=chance*10;
 }
 void update(int score)
 {
	sc+=score;
	timesplayed++;
 }
 int getscore()
 {
	 return sc;
 }
 int gettimesplayed()
 {
	 return timesplayed;
 }
};

class movies
{
  char m_name[50];
  char m_actor[50];
  char m_actress[50];
  char m_villain[50];

  public:

  char* name()
  {
	return m_name;
  }

  void mname1()
  {
	cout<<m_name;
  }

  void aname1()
  {
	cout<<m_actor;
  }

  void asname1()
  {
	cout<<m_actress;
  }

  void vname1()
  {
	cout<<m_villain;
  }

  void mname(char name[50])
  {
	strcpy(m_name,name);
  }

  void aname(char actor[50])
  {
	strcpy(m_actor,actor);
  }

  void asname(char actress[50])
  {
	strcpy(m_actress,actress);
  }

  void vname(char villain[50])
  {
	strcpy(m_villain,villain);
  }

  int check(char ch, int last);

}m;

int movies::check(char ch, int last)
{
	int pos=-1;
	for(int i=last;i<strlen(m_name);i++)
	{
		if(ch==m_name[i])
		{
			pos=i;
			break;
		}
	}
	return pos;
}

void main()
{
  ifstream fin1("c:\\game12A\\movie.txt",ios::in);
  ifstream fin2("c:\\game12A\\actor.txt",ios::in);
  ifstream fin3("c:\\game12A\\actress.txt",ios::in);
  ifstream fin4("c:\\game12A\\villain.txt",ios::in);
  //fstream score("c:\\game12A\\score.dat",ios::in|ios::out|ios::binary);
  fstream winner;

  clrscr();
  cout<<"\t\t\t\tHELLO THERE!";
  cout<<"\n\t\tWe WELCOME you to an AWESOME game called";
  textcolor(GREEN + BLINK);
  cout<<"\n\n\t\t\t\t";
  cprintf(" BOLLYWOOD ");
  cout<<"\n\t\t\t\t";
  cprintf(" ~~~~~~~~~ ");

  textcolor(WHITE);
  cout<<"\n\nSo before you start playing this game...\n\nHere are some important rules:";
  cout<<endl<<endl<<"\n1.This is a game in which you have to \'GUESS\' the movie name.";
  cout<<endl<<endl<<"2.You can only enter \'ONE\' letter at a time.";
  cout<<endl<<endl<<"3.You will get only \'9\' chances.";
  cout<<endl<<endl<<"4.If you get stuck in between, you are provided with only \'THREE\' hints.";
  cout<<endl<<endl<<"5.Press \'1\'to get hints.";
  textcolor(CYAN + BLINK);
  cout<<endl<<"\n\n";
  cprintf("NOW LETS GET STARTED!");
  getch();

  textcolor(WHITE);
  randomize();
  int n,i,l,h,pos,chance,swap,hint,check;
  char choice,ch,hchoice;
  char hname[30],line1[30],line2[30],line3[30],line4[30];
  int hscore;
  int exch;
  player temp1;
  char temp[50], extra[50];

  do
  {
	player p1,p;
	clrscr();
	chance=9;
	hint=0;
	n=random(1000);
	n=n%10;
	fin1.seekg(0,ios::beg);
	for(int q=0;q<=n;q++)
	{
	  fin1.getline(line1,30);
	  fin2.getline(line2,30);
	  fin3.getline(line3,30);
	  fin4.getline(line4,30);
	}
	m.mname(line1);
	m.aname(line2);
	m.asname(line3);
	m.vname(line4);
	strcpy(temp,m.name());
	for(i=0;i<strlen(temp);i++)
	{
		if(temp[i]==' ')
			{
			 extra[i]='|';
			 temp[i]='|';
			}
		else if(temp[i]=='a'||temp[i]=='e'||temp[i]=='i'||temp[i]=='o'||temp[i]=='u')
			extra[i]=temp[i];
		else
			extra[i]='_';
		cout<<extra[i]<<" ";
	}
       cout<<endl;
       delay(1000);

       while(chance>0)
       {
	repeat:
	swap=0;
	cout<<"Enter a letter which you think can fit in the above given movie name:";
	cin>>ch;

	if(ch=='1'&&hint<3)
	 {
		if(hint>=3)
		{
			cout<<endl<<"You are out of HINTS!";
			delay(2000);
		}

		hint++;
		//chance++;
		cout<<"\nWhich hint do you want:\n\n";
		cout<<"1.actor name\n2.actress name\n3.villain name\n";
		cout<<"Enter your choice=";
		cin>>h;
		switch(h)
		{
			case 1 : m.aname1();
				   delay(3000);
				  break;
			case 2 : m.asname1();
				   delay(3000);
				  break;
			case 3 : m.vname1();
				   delay(3000);
				  break;
			default: cout<<"Invalid Choice";
				 delay(2500);
		}
	 }

	else if(isdigit(ch))
	 {
		cout<<"Enter an ALPHABET and \'1\' in case if you want a hint!";
		delay(3000);
	 }

	else
	 {
		 for(int k=0;k<strlen(m.name());k++)
		 {
			pos=m.check(ch,k);
			if(pos!=-1)
			{
				extra[pos]=ch;
				swap++;
			}
		 }
	 }

	if(swap==0)
	{
		if(ch!='1')
			chance--;
		if(chance==0)
		{
			clrscr();
			textcolor(RED);

			cout<<'\a';
			cout<<"\n\n\n\n\n\n\n\n\n\n\n\t\t\t\t";
			cprintf("   YOU LOSE!");

			delay(2000);
			textcolor(WHITE);
			break;
		}
	}
	clrscr();

	for(i=0;i<strlen(m.name());i++)
	{
		cout<<extra[i]<<" ";
	}

	cout<<endl;
	cout<<"You have "<<chance<<" chances left!"<<endl;
	delay(2000);
	check=0;
	for(int a=0;a<strlen(temp);a++)
	{
		if(extra[a]=='_')
		 {
			  check++;
			  goto repeat;
		 }
	}

	if(chance>0 && check==0)
	{
		 clrscr();
		 textcolor(13);

		 cout<<"\n\n\n\n\n\n\n\n\n\n\t\t\t\t";
		 cprintf("     YOU WIN!");
		 cout<<endl<<endl<<'\t'<<'\t'<<'\t'<<"    ";
		 textcolor(CYAN);
		 cprintf("\t\t\t\t CONGRATULATIONS \t\t\t\t");
		 delay(2000);

		 textcolor(WHITE);
		 clrscr();

		 p.score(chance);
		 p.getdata();
		 cout<<endl<<p.getname()<<", your Score:";
		 cout<<p.getscore()<<endl;
		 winner.open("c:\\game12A\\winner.dat",ios::in|ios::out|ios::binary);
		 winner.seekg(0,ios::end);
		 int b=winner.tellg()/sizeof(p);
		 //cout<<b<<"bytes\n";

		 if(b==0)
			winner.write((char*)&p,sizeof(p));
		 else
		 {
			winner.seekg(0,ios::beg);
			winner.read((char*)&p1,sizeof(p1));
			int found=0;
			while(!winner.eof())
			 {
				if(strcmpi(p1.getname(),p.getname())==0)
				{
					//p1.score(p.getscore()/10);
					p1.update(p.getscore());
					cout<<p1.getscore()<<p1.getname();
					winner.seekg(winner.tellg()-sizeof(p1),ios::beg);
					winner.write((char*)&p1,sizeof(p1));
					found=1;
					break;
				}
				winner.read((char*)&p1,sizeof(p1));
			}
		 if(found==0)
		 {
			winner.close();
			winner.open("c:\\game12A\\winner.dat",ios::in|ios::out|ios::binary);
			winner.seekg(0,ios::end);
			//cout<<"\nhello"<<winner.tellg()/sizeof(p);
			winner.write((char*)&p,sizeof(p));
		 }

		 }
		 //winner.close();
		  player pl[10];
		  winner.seekg(0,ios::beg);
		  winner.read((char*)&p1,sizeof(p1));
		  int cnt=0;
		  while(!winner.eof())
		  {
			pl[cnt++]=p1;
			winner.read((char*)&p1,sizeof(p1));
		  }

		  cout<<cnt<<"records\n";

		  for(int y=0;y<cnt-1;y++)
		  {
			for(int z=0;z<cnt-1-y;z++)
			{
			exch=0;
			if(pl[z+1].getscore()>pl[z].getscore())
			  {
				   temp1=pl[z];
				   pl[z]=pl[z+1];
				   pl[z+1]=temp1;
				   exch++;
			  }
			}
			if(exch==0)
			  break;
		  }

		 cout<<"\n\nOur previous winners:"<<endl;


		 int i=0;
		 for (i=0;i<cnt;i++)
		 {
			cout<<i+1<<" "<<pl[i].getname()<<":"<<pl[i].getscore()<<":"<<pl[i].gettimesplayed()<<endl;
		 }

		 getch();
		 break;
	}

	   }
	clrscr();
	winner.close();
	cout<<"Do you want to play again?(y/n):";
	cin>>choice;
  }while(choice=='y');

  clrscr();

  cout<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl;
  cout<<'\t'<<'\t'<<'\t'<<"     ";
  textcolor(YELLOW + BLINK);
  cprintf("\t THANKS for PLAYING \t");
  textcolor(WHITE);
  delay(2000);

}
