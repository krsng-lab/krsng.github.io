# krsng.github.io

# Problem Set 1: mario-less

## Understanding the Criteria
In a file called mario.c in a folder called mario-less, implement a program in C that recreates that pyramid, using hashes (#) for bricks, as in the below:
```
       #
      ##
     ###
    ####
   #####
  ######
 #######
########
```
But prompt the user for an int for the pyramid’s actual height, so that the program can also output shorter pyramids like the below:
```
  #
 ##
###
```
Re-prompt the user, again and again as needed, if their input is not greater than 0 or not an int altogether.

## First, let's start with including our libraries.
```
#include <cs50.h>
#include <stdio.h>
```
## Establishing the Conditions 


## Examining the Pattern 
There are many ways you can interpret the output required from your code. Consider the following: 
```
·······#
······##
·····###
····####
···#####
··######
·#######
########
```
To better visualise this pattern, regard the empty spaces to the right as dots.

```
    for (int i = 1; i <= height; i++)
    {
        for (int j = 0; j < height - i; j++)
        {
            // Print the empty spaces
            printf(" ");
        }
        // Print the hashes
        for (int j = 0; j < i; j++)
        {
            printf("#");
        }
        printf("\n");
    }
```
> [!NOTE]
> We are printing an empty space instead of "·". 



 
