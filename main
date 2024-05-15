```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        String[] arr1 = {" ", " ", " "};
        String[] arr2 = {" ", " ", " "};
        String[] arr3 = {" ", " ", " "};

        String[][] playGround = {arr1, arr2, arr3};
        
        boolean gameOver = false;

        Scanner scanner = new Scanner(System.in);

        while (!gameOver) {
            displayBoard(playGround);

            System.out.println("You are player 1, please choose your move (row:column): ");
            String player1 = scanner.nextLine();
            String[] moveSplit = player1.split(":");
            int row1 = Integer.parseInt(moveSplit[0]) - 1;
            int col1 = Integer.parseInt(moveSplit[1]) - 1;
            pushMoves(playGround, row1, col1, "X");

            if (checkForWin(playGround)) {
                System.out.println("Player 1 wins!");
                gameOver = true;
                break;
            }

            displayBoard(playGround);

            System.out.println("You are player 2, please choose your move (row:column): ");
            String player2 = scanner.nextLine();
            String[] moveSplit2 = player2.split(":");
            int row2 = Integer.parseInt(moveSplit2[0]) - 1;
            int col2 = Integer.parseInt(moveSplit2[1]) - 1;
            pushMoves(playGround, row2, col2, "O");

            if (checkForWin(playGround)) {
                System.out.println("Player 2 wins!");
                gameOver = true;
                break;
            }

        }
    }

    public static void displayBoard(String[][] playGround) {
        System.out.println("   1  2  3");
        for (int i = 0; i < playGround.length; i++) {
            System.out.print((i + 1) + "|");
            for (int j = 0; j < playGround[i].length; j++) {
                System.out.print(playGround[i][j] + " |");
            }
            System.out.println("\n-----------");
        }
    }

    public static void pushMoves(String[][] playGround, int row, int col, String symbol) {
        if (playGround[row][col].equals(" ")) {
            playGround[row][col] = symbol;
        } else {
            System.out.println("This cell is already occupied. Please choose another move.");
        }
    }

    public static boolean checkForWin(String[][] playGround) {
        for (int i = 0; i < playGround.length; i++) {
            if (playGround[i][0].equals(playGround[i][1]) &&
                    playGround[i][1].equals(playGround[i][2]) &&
                    !playGround[i][0].equals(" ")) {
                return true;
            }
        }

        for (int j = 0; j < playGround[0].length; j++) {
            if (playGround[0][j].equals(playGround[1][j]) &&
                    playGround[1][j].equals(playGround[2][j]) &&
                    !playGround[0][j].equals(" ")) {
                return true;
            }
        }

        
        if ((playGround[0][0].equals(playGround[1][1]) &&
                playGround[1][1].equals(playGround[2][2]) &&
                !playGround[0][0].equals(" ")) ||
                (playGround[0][2].equals(playGround[1][1]) &&
                        playGround[1][1].equals(playGround[2][0]) &&
                        !playGround[0][2].equals(" "))) {
            return true;
        }

        boolean isGameIsTie = true;
        for (int i = 0; i < playGround.length; i++) {
            for (int j = 0; j < playGround[i].length; j++) {
                if (playGround[i][j].equals(" ")) {
                    isGameIsTie = false;
                    break;
                }
            }
            if (!isGameIsTie) {
                break;
            }
        }
        return isGameIsTie;
    }
}
```
