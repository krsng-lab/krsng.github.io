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
We want our height to be a positive integer between 1 and 8, inclusive. 
This can be achieved by utilising the do-while loop. 
```
    int height;
    do
    {
        height = get_int("Height: ");
    }
    while (height <= 0 || height > 8);
```
Let the row number be _i_. 
```
    for (int i = 1; i <= height; i++)
```
Such that there will be _i_ number of rows starting from row 1 until _i_ is equal to the value of the height. 

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

## Deducing the Pattern

Suppose you input a height of 3. 
```
··#
·##
###
```
In row 1, there are 2 dots and 1 hash.

In row 2, there are 1 dot and 2 hashes.

In row 3, there are 0 dots and 3 hashes. 

We can deduce a pattern such that each row has the number of dots corresponding to less than the total height - the row the dots are in, _i_.

We can also deduce a pattern such that each row has the number of hashes corresponding to less than the row the dots are in. 

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

> [!CAUTION]
> We are printing an empty space instead of "·". The dot is there simply as a visualisation tool.

> [!IMPORTANT]
> We must end off our code with printf(“\n”) to move to the next line after printing each row of the pyramid.
> Otherwise, our output would end up like this:
> ```
>  # #####
>  ```


## Final Results
```
#include <cs50.h>
#include <stdio.h>
int main(void)
{
    // Prompt the user for the pyramid's height
    int height;
    do
    {
        height = get_int("Height: ");
    }
    while (height <= 0 || height > 8);

    // Print a pyramid of that height
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
}
```




 
