#include <stdio.h>
float unit(float chrg, float unit)
{
   if (unit>199)
   chrg=1.50;
   if(unit>=250)
   chrg=1.60;
   if(unit <400)
   chrg=1.60;
   if(unit>=450)
   chrg=1.85;
   if(unit <600)
   chrg=1.85;
   if (unit>=600 )
   chrg=2.00;
   return chrg;
}


float Unit_charge(float a, float b)
{
    float result;
    result = a*b;
    return result;
}


float surcharge( float bill)
{
    float equivalent;
    if (bill>400)
    equivalent=bill/10;
    else
    equivalent= 100;
    return equivalent;
}


float total_bill(float e, float i)
{
    float sum;
    sum= e+i;
    return sum;
}


int main()
{
    int ID, count;
    float  charge, c, d,unitcharge, srchrg, result;
    printf("Input Customer ID: ");
    scanf("%d", &ID);
    
    printf("Input the unit consumed by the customer: ");
    scanf("%d", &count);
    
    printf("\n\n[Electricity Bill]\n");
    printf("Costumers ID#                   : %d\n", ID);
    printf("Unit Consumed                   : %d\n", count);
    charge=unit(c, count);
    unitcharge=Unit_charge(charge,count);
    printf("Unit charges @P. %.2f per unit  :P %.2f\n", charge,unitcharge);
    srchrg= surcharge(unitcharge);
    printf("Surcharge Amount                :P %.2f\n",srchrg);
    result= total_bill(unitcharge,srchrg);
    printf("Total Customer Bill             :P %.2f\n", result);
    
    
    return 0;
}
