# tictactoe
import java.util.*;
public class tictactoenew
{
    public static void main(String args[])
    { 
        String rerun = "yes";

        while(rerun.equalsIgnoreCase("yes"))
        {
            System.out.print("welcome!");

            int i,j,k=1,l,m;
            String player1,player2;
            Scanner sc = new Scanner(System.in);
            String mat[][] = new String[3][3];
            System.out.println();
            System.out.print("enter player1 name: ");
            player1 = sc.next();
            System.out.print("enter player2 name: ");
            player2 = sc.next();
            System.out.println();


            for(i=0 ; i<3 ; i++)
            {
                for(j=0 ; j<3 ; j++)
                {
                    mat[i][j] = " - ";
                }
            }

            for (i=0 ; i<3 ; i++)
            {
                for(j=0 ; j<3 ; j++)
                {
                    System.out.print(mat[i][j]);
                }
                System.out.print("\t");
                for(l=0 ; l<3 ; l++)
                    {
                        System.out.print(" " + k + " ");
                        k++;
                    }
                System.out.println();
            }
            int winflag = 0;
            int flag = 0;
            int r,c;
            int ctr = 0;
            while(ctr < 9)  
            {
                System.out.println();
                System.out.print("enter number according to the matrix beside the game: ");
                m = sc.nextInt();
                c = (m-1)%3;
                r = (m-1)/3;
                if(m > 9 || m < 1)
                {
                    System.out.print("Please enter numbers from 1-9 ");
                    ctr--;
                    System.out.println();
                }
                else
                {
                    if(mat[r][c] == " x " || mat[r][c] == " o ")
                    {
                        System.out.print("player has already entered in that position. Please enter somewhere else!");
                        System.out.println();
                        ctr--;
                    }
                    else
                    {
                        if (flag == 0)
                        {
                            mat[r][c] = " x ";
                            flag = 1;
                        }
                        else if (flag == 1)
                        {
                            mat[r][c] = " o ";
                            flag = 0;
                        }
                    }
                }

                if (mat[0][0] == mat[1][0] && mat[1][0] == mat[2][0] && mat[2][0] != " - ")
                {
                    winflag = 1;
                
                }
                if (mat[0][1] == mat[1][1] && mat[1][1] == mat[2][1] && mat[2][1] != " - ")
                {
                    winflag = 1;
                }
                if (mat[0][2] == mat[1][2] && mat[1][2] == mat[2][2] && mat[2][2] != " - ")
                {
                    winflag = 1;
                }
                if (mat[1][0] == mat[1][1] && mat[1][1] == mat[1][2] && mat[1][2] != " - ")
                {
                    winflag = 1;
                }
                if (mat[2][0] == mat[2][1] && mat[2][1] == mat[2][2] && mat[2][2] != " - ")
                {
                    winflag = 1;
                }
                if (mat[0][0] == mat[1][1] && mat[1][1] == mat[2][2] && mat[2][2] != " - ")
                {
                    winflag = 1;
                }
                if (mat[0][2] == mat[1][1] && mat[1][1] == mat[2][0] && mat[2][0] != " - ")
                {
                    winflag = 1;
                }
                if (mat[0][0] == mat[0][1] && mat[0][1] == mat[0][2] && mat[0][0] != " - ")
                {
                    winflag = 1;
                }
                k = 1;
            
                for (i=0 ; i<3 ; i++)
                {
                for(j=0 ; j<3 ; j++)
                    {
                        System.out.print(mat[i][j]);
                    }
                    System.out.print("\t");
                    for(l=0 ; l<3 ; l++)
                    {
                        System.out.print(" " + k + " ");
                        k++;
                    }
                    System.out.println();
                }

                System.out.println();
                if(winflag == 1 && flag == 1)
                {
                    System.out.print(player1+" wins");
                    System.out.println();
                    break;
                }
                if (winflag == 1 && flag == 0)
                {
                    System.out.print(player2+" wins");
                    System.out.println();
                    break;
                }
                ctr++;
            }
            if (ctr == 9)
            {
                System.out.print("match tied");
                System.out.println();
                System.out.println();            
            }
            System.out.print("Do you want to play again? ");
            System.out.print("If yes, enter yes/Yes :  ");
            rerun = sc.next();
        }
    }
}
