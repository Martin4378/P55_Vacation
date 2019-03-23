# P55_Vacation

import java.util.Scanner;

public class P55_Vacation {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        double needMoneyForVocation = Double.parseDouble(scanner.nextLine());
        double availableMoney = Double.parseDouble(scanner.nextLine());
        int countAllDays = 0;
        double saveMoney = availableMoney;
        int countSpend = 0;


        while (!(saveMoney >= needMoneyForVocation)){
            countAllDays++;
            String whatToDo = scanner.nextLine();
            double money = Double.parseDouble(scanner.nextLine());
            switch(whatToDo){
                case "spend":
                    countSpend++;
                    if(countSpend == 5){
                        System.out.println("You can't save the money.");
                        System.out.println(countAllDays);
                        return;
                    }
                    if(money < saveMoney){
                        saveMoney -= money;
                    }else {
                        saveMoney = 0;
                    }
                    break;
                case "save":
                    countSpend = 0;
                    saveMoney += money;
                    break;
            }
        }
        System.out.printf("You saved the money for %d days.", countAllDays);
    }
}
