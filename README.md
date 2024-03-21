# This code was created as an assignment for ICS4UA: AP Computer Science.
### Language: Java
```java
package store;
import java.util.Scanner;
import java.time.LocalDateTime;
import java.time.format.DateTimeFormatter;
public class StoreProject {
	
	public static void main(String[] args) {

	double priceofBananas = 0.75; // one banana
	double priceofCarrots = 1.00; // one carrot
	double priceofChocolates = 1.50; // one chocolate
	boolean promotion = false;
	boolean restart = true;
	
	LocalDateTime currentTime = LocalDateTime.now();
	DateTimeFormatter formatted = DateTimeFormatter.ofPattern("yyyy-MM-dd");
	String date = currentTime.format(formatted);
	Scanner scanner = new Scanner(System.in);

	while (restart = true) {
	
	
	System.out.print("Hello shopper, and welcome to the store!\n\nHint: Use the code 'CHOCO' at checkout for $1 off chocolates!\n\n\nLet's get some fruit. How many bananas do you want? (Max. 9) ");
	
	int numberofBananas = scanner.nextInt();
	if (numberofBananas < 0 || numberofBananas > 9) {
		numberofBananas = 9;
		System.out.println("Unfortunately, you've chosen a number too low or high. Enjoy 9 bananas instead.");
	}
	System.out.print("Great, let's get some veggies! How many pieces of carrot do you want? (Max. 9) ");
	int numberofCarrots = scanner.nextInt();
	if (numberofCarrots < 0 || numberofCarrots > 9) {
		numberofCarrots = 9;
		System.out.println("Unfortunately, you've chosen a number too low or high. Enjoy 9 carrots instead.");
	}
	System.out.print("Let's end off with something sweet! How many chocolates do you want? (Max. 9) ");
	int numberofChocolates = scanner.nextInt();
	if (numberofChocolates < 0 || numberofChocolates > 9) {
		numberofChocolates = 9;
		System.out.println("Unfortunately, you've chosen a number too low or high. Enjoy 9 chocolates instead.");
	}
	scanner.nextLine();
	priceofBananas = priceofBananas * numberofBananas;
	priceofCarrots = priceofCarrots * numberofCarrots;
	priceofChocolates = priceofChocolates * numberofChocolates;
	
	System.out.print("Do you have a promotion code? If so, what is it? Type NO if none. ");
	String promoCode = scanner.nextLine();
	
	if(promoCode.equals("CHOCO") && numberofChocolates > 0) {
		priceofChocolates = priceofChocolates - 1;
		promotion = true;
	} else if (promoCode.equals("NO")) {
		System.out.println("No promotion code was applied!");
		promotion = false;
	} else if (!promoCode.equals("NO")) {
		System.out.println("An error occurred, no promotion code was applied!");
		promotion = false;
	}
	

	double subtotal = priceofBananas + priceofCarrots + priceofChocolates;
	double total = subtotal * 1.13;
	double tax = total - subtotal;
	tax = Math.round(tax * 100.0) / 100.0;
	total = Math.round(total * 100.0) / 100.0;
	
	
	
	
	System.out.println("\n\nThank you for shopping at Walmart!\nHere is your receipt:\n");
	
	
	System.out.println(" ___________________________");
    System.out.println("/          Walmart          \\");
    System.out.println("|         " + date + "        |");
    System.out.println("|          RECEIPT          |");
    System.out.println("|---------------------------|");
    System.out.println("|   Item  | Amount |  Price |");
    System.out.println("|---------------------------|");
    System.out.println("|  Bananas	| " + numberofBananas + "  | " + priceofBananas + " |");
    System.out.println("|  Carrots      | " + numberofCarrots + "  | " + priceofCarrots + "  |");
    System.out.println("|  Chocolates   | " + numberofChocolates + "  | " + priceofChocolates + "  |");
    System.out.println("|---------------------------|");
    if (promotion == true) {
    System.out.println("|  Promotion   |  " + "-$1.00    |");
    }
    System.out.println("|  Subtotal    |  " + "$" + subtotal + "    |");
    System.out.println("|  Tax (13%)   |  " + "$" + tax + "     |");
    System.out.println("|---------------------------|");
    System.out.println("|  Total       |  " + "$" + total + "    |");
    System.out.println("|  Cashier     |  Ayaan     |");
    System.out.println("|  Register    |  08        |");
    System.out.println("\\__________________________/");
	
    System.out.println("\nType RESTART to restart this game!");
    String restartConfirmation = scanner.nextLine();
	if (restartConfirmation.equals("RESTART")) {
		System.out.println("\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n");
		restart = true;
	} else if (restartConfirmation.equals("DONE")) {
		System.out.println("Thank you for shopping! Enjoy your purchases!");
		restart = false;
	}
    
	}
	
	
	
	
	}

}
```
