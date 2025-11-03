//The Smart Canteen Billing System
#include<stdio.h> // preprocessor directiry
int main()
{
int customers, i, j, code, items, quantity; //variables
    float price = 0, total_price = 0, discount = 0;
    float customer_total = 0, total_revenue = 0, final_bill = 0;
 printf("Enter no of customers : ");
 scanf("%d",&customers);
 for (i = 1; i <= customers; i++) {
        customer_total = 0; // reset totals per customer
        discount = 0;
        printf("\n--- Customer %d ---\n", i);
        printf("Code Item Name Price\n");
   printf(" 1  Sandwich = 80 \n 2  Burger = 120 \n 3  PizzaSlice = 150 \n 4  Coffee = 60 \n 5  Juice = 50\n");
        printf("\nEnter number of items: ");
        scanf("%d", &items);
        for (j = 1; j <= items; j++) {
            printf("Enter Item code: ");
            scanf("%d", &code);
            printf("Enter quantity: ");
            scanf("%d", &quantity);
            switch (code) {
                case 1:
                    printf("Sandwich*%d = %d\n", quantity, 80 * quantity);
                    price = 80;
                    break;
                case 2:
                    printf("Burger*%d = %d\n", quantity, 120 * quantity);
                    price = 120;
                    break;
                case 3:
                    printf("Pizza Slice*%d = %d\n", quantity, 150 * quantity);
                    price = 150;
                    break;
                case 4:
                    printf("Coffee*%d = %d\n", quantity, 60 * quantity);
                    price = 60;
                    break;
            case 5:
            printf("Juice*%d = %d\n", quantity, 50 * quantity);
            price = 50;
            break;
            default:
            printf("Invalid Code!\n");
            price = 0;
            break;
            }
            total_price = price * quantity;
            customer_total += total_price;
        }
        if (customer_total > 500) {
            discount = 0.1 * customer_total;
        } else {
            discount = 0;
        }
        final_bill = customer_total - discount;
        total_revenue += final_bill;
        printf("\n Customer %d Bill:\n", i);
        printf("Total: %.2f\n", customer_total);
        if (discount > 0)
            printf("Discount (10%%): %.2f\n", discount);
        printf("Final Bill: %.2f\n", final_bill);
    }
    printf("\n Canteen Summary \n");
    printf("Total Customers Served: %d\n", customers);
    printf("Total Revenue: %.2f\n", total_revenue);
    return 0;
}
//summary
// In this concept we learnt the Nested loop for customer's
// if-else and switch conditions for logic
// Arithmetic operations
