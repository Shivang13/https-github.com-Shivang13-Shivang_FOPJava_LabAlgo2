# https-github.com-Shivang13-Shivang_FOPJava_LabAlgo2

package practice;

import java.util.Scanner;

import java.util.Scanner;

public class paymenttransaction {
    public static int targetAchieved(int[] transactions, int target) {
        int runningSum = 0;
        for (int i = 0; i < transactions.length; i++) {
            runningSum += transactions[i];
            if (runningSum >= target) {
                return i + 1;
            }
        }
        return -1;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter the size of the transaction array: ");
        int size = scanner.nextInt();

        int[] transactions = new int[size];
        System.out.print("Enter the values of the array: ");
        for (int i = 0; i < size; i++) {
            transactions[i] = scanner.nextInt();
        }

        System.out.print("Enter the total number of targets that need to be achieved: ");
        int numTargets = scanner.nextInt();

        int[] targets = new int[numTargets];
        for (int i = 0; i < numTargets; i++) {
            System.out.print("Enter the value of target: ");
            targets[i] = scanner.nextInt();
        }

        for (int target : targets) {
            int transactionsNeeded = targetAchieved(transactions, target);
            if (transactionsNeeded != -1) {
                System.out.println("Target achieved after " + transactionsNeeded +
                        " transaction(s)");
            } else {
                System.out.println("Target is not achieved.");
            }
        }
    }
}


