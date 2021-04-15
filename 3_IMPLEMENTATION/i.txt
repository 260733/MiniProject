#include <stdio.h>
#include<stdlib.h>
#include <math.h>

float loanAmount,interestRate,Discount,i,loanPayment; //global variables

int years;

void loanDetails(void); //input from user regarding the loan
float annualRate(void);// interest rate 
float discount(void); //discount to be added

int main() 
{
    int choice;
    printf("Enter your choice from 1 to 3\n");
    scanf("%d",&choice);
    switch(choice)
    {
    Case1:
    {
	float principal, rate, time, emi;

	printf("Enter principal: ");
	scanf("%f",&principal);

	printf("Enter rate: ");
	scanf("%f",&rate);

	printf("Enter time in year: ");
	scanf("%f",&time);

	rate=rate/(12*100);	/*one month interest*/
	time=time*12; /*one month period*/


	emi= (principal*rate*pow(1+rate,time))/(pow(1+rate,time)-1);

	printf("Monthly EMI is= %f\n",emi);
    }
    Case2:
    {
         loanDetails(); //called three functions
    annualRate();
    discount();

    loanPayment = (loanAmount)/(Discount); //formula for monthly payments

    printf("\nthe monthly loan payment is %f",loanPayment);

    return EXIT_SUCCESS;
    }
    }

    return 0;
}



void loanDetails(void) //taking input from user
{
    printf("please enter Total Loan Amount: ");
    scanf("%f",&loanAmount);
    printf("please enter the number of years: ");
    scanf("%d",&years);
    printf("please enter the annualrate to be applied: ");
    scanf("%f",&interestRate);
}

float annualRate(void) //calculated annual rate
{
    float *ann;
    ann = &interestRate;
    i = ((*ann)/(100))/12;
    printf("the value for %d years is %f",years,i);
    return i;
}

float discount(void) //calculated dicount
{    
    float *x,y;
    x = &i;
    y = 1 + *x;
    int n = years*12;

    float topD = (pow((y),n)-1);
    float botD = (y-1)*pow((y),n);
    Discount = topD/botD;
    printf("\nthe value of discount is : %f",Discount);
    return Discount;
}
