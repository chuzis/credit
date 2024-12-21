#include <stdio.h>
#include <cs50.h>

int main(void)
{
    long int number = get_long ("Number: ");
    long int temp_number = number;
    long int amex15, visa13, visa16, master16;
    amex15 = visa13 = visa16 = master16 = 0;
    int checksum, digit, digit_sum, digit_times_two, digit_times_two_sum, digit_over_ten_sum, digit_first_digit, digit_second_digit;
    checksum = digit = digit_sum = digit_times_two = digit_times_two_sum = digit_over_ten_sum = digit_first_digit = digit_second_digit = 0;
    amex15 = (number * 0.0000000000001);
    visa13 = (number * 0.000000000001);
    visa16 = (number * 0.000000000000001);
    master16 = (number * 0.00000000000001);

    for (int i = 1; i <= 16; i+=2)
        {
            temp_number = temp_number * 0.1;
            digit = temp_number % 10;
            temp_number = temp_number - digit;
            temp_number = temp_number * 0.1;
            digit_times_two = (digit * 2);
//            printf("Isolated digit number %i", (i+1));                        //     FOR DEBUGGING
//            printf(" (%i)", digit);                                           //     FOR DEBUGGING
//            printf(" ");                                                      //     FOR DEBUGGING
//            printf("times two: %i\n", digit_times_two);                       //     FOR DEBUGGING

            if (digit_times_two >= 10)
                {
                    digit_first_digit = digit_times_two / 10;
                    digit_second_digit = digit_times_two % 10;
                    digit_over_ten_sum = (digit_first_digit + digit_second_digit);
//                  printf("sum of two digits is %i\n", digit_over_ten_sum);    // FOR DEBUGGING
                    digit_times_two_sum = (digit_times_two_sum + digit_over_ten_sum);
                }

            else
                {
                    digit_times_two_sum = (digit_times_two_sum + digit_times_two);
                }
            if (temp_number <=0)
                {
                    break;
                }


        }
//    printf("Variable digit_times_two_sum equals %i\n", digit_times_two_sum); // FOR DEBUGGING
    digit = 0;
    temp_number = number;
//    printf("Variable temp_number equals %li\n", temp_number);                // FOR DEBUGGING
    for (int j = 1; j <= 16; j += 2)
       {

        digit = temp_number % 10;
 //       printf("Number : %li\n", temp_number);                               // FOR DEBUGGING
        temp_number = temp_number - digit;
        temp_number = temp_number * 0.01;
        digit_sum = (digit_sum + digit);
//        printf("Isolated digit number %i", (j));                             // FOR DEBUGGING
//        printf(": "),                                                        // FOR DEBUGGING
//        printf("%i\n", digit);                                               // FOR DEBUGGING


        if (temp_number <= 0)
            {
                break;
            }
       }


//    printf("Variable digit_sum equals %i\n", digit_sum);                     // FOR DEBUGGING
    checksum = (digit_sum + digit_times_two_sum);
//    printf ("Variable checksum equals %i\n", checksum);                      // FOR DEBUGGING
    if (checksum % 10 == 0)
        {
        if (amex15 == 34 || amex15 == 37)
        {
            printf("AMEX\n");
        }

        else if (visa13 == 4 || visa16 == 4)
        {
            printf("VISA\n");
        }

        else if (master16 >=51 && master16 <= 55)
        {
             printf("MASTERCARD\n");
        }

        else
        {
            printf("INVALID\n");
        }
        }
    else
    {
        printf("INVALID\n");
    }



return 0;
}
