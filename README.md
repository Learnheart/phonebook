#include <stdio.h>
#include <string.h> 
#include <stdlib.h>
		
//Declare the structures 
struct phone_book {
	char name [30];
	char country[20];
	long int mb_phone [13];
	char email [30] ;
	char group [30];
};
 
//Declare custom datatypes
typedef struct phone_book address; 

/* Define all functions */

void menu();
void record_list();
void add_contact(); 
void update_contact();
void search();
void delete_contact();
void delete_all();
void take_input (person *p); //pointer 

/* Application start from here*/
int main ()  {
	void start();
	return 0;
}

/*This used to customer decide their choice in phone book app */
void start() {
	int choice;
	while (1) {		//if condition is true
		menu();
		scanf ("%d", &choice);
		switch (choice) (
			case 1: 
				record_list();
				getchar();
				getchar();
				break;
			case 2:
				add_contact();
				getchar();
				getchar();
				break;
			case 3:
				update_contact();
				getchar();
				getchar();
				break();
			case 4:
				search();
				getchar();
				getchar();
				break;
			case 5:
				delete_contact();
				getchar();
				getchar();
				break;
			case 6: 
				delete_all();
				getchar();
				getchar();
				break();
			default:
				getchar();
				getchar();
				exit(1);
		)
	}
}

/* Create menu form include:
	1. Check record list
	2. Add more contact
	3. Updating contact
	4. Search details
	5. Delete contact
	6. Delate all
*/
void menu() {
	system ("cls"); //delete all the previous stuffs
	
//FrontEnd of Menu - start//
	printf ("\n");
	printf (" \t \t \t ********************************************************** \n");
	printf (" \t \t \t *                                                        * \n");
	printf (" \t \t \t *                        MAIN MENU                       * \n");
	printf (" \t \t \t *                                                        * \n");
	printf (" \t \t \t ********************************************************** \n");
	
	printf ("\n");
	printf (" \t \t \t Please select the button: \n"); 
	printf ("\n");
	printf (" \t \t \t \t 1. Open phonebook list \n");
	printf ("\n");
	printf (" \t \t \t \t 2. Add new contact \n");
	printf ("\n");
	printf (" \t \t \t \t 3. Update contact \n");
	printf ("\n");
	printf (" \t \t \t \t 4. Search contact detail \n");
	printf ("\n");
	printf (" \t \t \t \t 5. Delete a contact \n");
	printf ("\n");
	printf (" \t \t \t \t 6. Delete all contacts from phonebook list \n");
	printf ("\n");
	printf ("\n");
	printf (" \t \t \t \t \t _Enter your choice: ");
	
//Menu frontend - end//
}

/* A function which user can add new contact into phonebook */
void add_contact()  {
	system ("cls");
	FILE *fp; 						//make the file oriented 
	fp = fopen ("phonebook", "a+");	//open this file to read and append 
	if (fp == NULL) {
		printf ("Please try again! \n");
		printf ("Press any key to continue");
		return;								//return the MAIN MENU
	}
	else {
		person p;
		take_input (&p); //take input from user
		fwrite (&p, sizeof(p), 1, fp); 		//we only adding 1 person in this file per time -> int n = 1
		fflush (stdin);						//for memory efficient
		fclose (fp);						//close this file
		system ("cls");
		printf ("Record added successfully! \n");
		printf ("Press any key to continue");
		
	}
}

/*This function used to take informations when user put it into app */
void take_input(person *p) {
	system ("cls");
	//test version used gets() 
	printf ("Enter name: ");
	gets (p -> name);
	printf ("Enter country: ");
	gets (p -> country);
	printf ("Enter phone number: ");
	gets (p -> mb_phone);
	printf ("Enter mail: ");
	gets (P -> mail);
	printf ("Enter group that contact belong to: ");
	gets (p -> group);
}

void record_list() {
	
}

