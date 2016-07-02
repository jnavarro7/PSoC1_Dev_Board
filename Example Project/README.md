  # PSoC1_Dev_Board
Custom PSoC1(CY8C21223-24SXI) Dev Board 

Place it directly onto a breadboard, program it with the MiniProg3 from Cypress Semiconductor.   
  

This example project uses digital pin P0(0) as a switch when taken to ground switches P1(0) high which can turn a transistor, LED, Etc. 



//----------------------------------------------------------------------------
// C main line
//----------------------------------------------------------------------------

#include <m8c.h>        // part specific constants and macros
#include "PSoCAPI.h"    // PSoC API definitions for all User Modules

static unsigned int i;

void main( void )
{
	while ( 1 )
	{
		if (PRT0DR & 0x01 ) //Checks the state of the button. If the button is pressed then it will execute.
		{
			PRT1DR &= ~ 0x01 ; //Turns the LED On.
		}
		else
		{
			PRT1DR |= 0x01 ; //Turns the LED Off.
		}
	}
}