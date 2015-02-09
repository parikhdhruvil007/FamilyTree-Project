# FamilyTree-Project
In this project, we created a family tree using family echo website and than we downloaded tree in GEDCOM format. After that open the
file in as .txt extention and read this file by writing a code in any programming language. Code below is in C++.
/*
Name: Dhruvil Parikh
Class: SSW-555-Agile Methods and Development
Instructor: Hugh Sheridan
Date Modified: 02/04/2015

Description of the Project:
	This Program will read the Gedcom file and than with each input line, it will print 3 output lines.
Output should look like:
	1) First line: Print whole line from Text file
	2) Second line: Print only level number Example: 0, 1, 2
	3) Third line: Pring TAG (IF VALID ONLY) Example: NAME, SEX, BIRTH...
*/
#include<iostream>
#include<fstream>
#include<string>
using namespace std;

int main()
{
	int levelnumber;
	int count = 0;
	string sentence;
	string tagPrint;
	string arguments;
	
	
	cout<<"\t DHRUVIL'S SHORT FAMILY TREE "<<endl;
	cout<<"\t ___________________________ "<<endl;
	
	ifstream fileName("testingTree4.txt");  //opens the requested Text File
	
	if(fileName.is_open())
	{
		do
		{
			getline (fileName,sentence);   //Captures the line from the Text File
			fileName >> levelnumber >> tagPrint >> arguments;	//Captures each word from Text file to distinguish
			cout<<levelnumber<<" "<<tagPrint<<" "<<arguments<<endl;
			cout<<levelnumber<<endl;
			if(levelnumber == 0 && count>=2)
			{
				cout<<" INVALID TAG "<<endl;	//Prints Invalid if the TAG does not satisfy the condition
			}
			else
				cout<<tagPrint<<endl;
			
			count++; 
		}
		while(fileName.good());
		fileName.close();
	}
	else
		cout<<" Cannot open the file: CHECK THE NAME AGAIN "<<endl<<endl;
	
	return 0;

	
	
}
