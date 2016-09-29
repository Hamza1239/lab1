# lab1


/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package matrixmultiplication;

/**
 *
 * @author haleem.bscs14seecs
 */
import java.util.Scanner;        // import lib / package
 
class MatrixMultiplication   
{
   public static void main(String args[])
   {
      int m, n, p, q, sum = 0, c, d, k;
 
      Scanner in = new Scanner(System.in);          // Creation of Object 'in'
      System.out.println("Enter the number of rows and columns of first matrix");   //Input number of rows & columns
      m = in.nextInt();
      n = in.nextInt();
 
      int first[][] = new int[m][n];          // Creating 2D array for 1st Matrix
 
     
 
      System.out.println("Enter the number of rows and columns of second matrix");   //Input number of rows & columns
      p = in.nextInt();
      q = in.nextInt();
      
       
 
      if ( n != p )               // if row != column show error
         System.out.println("Matrices with entered orders can't be multiplied with each other.");
      else
      {
         int second[][] = new int[p][q];              // Making the 2D array of same size of matrix 
         int multiply[][] = new int[m][q];            // Making the 2D array of same size of matrix 
         
         
         System.out.println("Enter the elements of first matrix");     // Input the values of 1st Matrix
 
      for ( c = 0 ; c < m ; c++ )
         for ( d = 0 ; d < n ; d++ )
            first[c][d] = in.nextInt();              // Populating the First matrix
 
        System.out.println("Enter the elements of second matrix");      // Input the values of 2nd Matrix
 
         for ( c = 0 ; c < p ; c++ )
            for ( d = 0 ; d < q ; d++ )
               second[c][d] = in.nextInt();          // Populating the Second matrix
 
         for ( c = 0 ; c < m ; c++ )
         {
            for ( d = 0 ; d < q ; d++ )
            {   
               for ( k = 0 ; k < p ; k++ )
               {
                  sum = sum + first[c][k]*second[k][d];        //  Main logic of multiplication using 3 for loops
               }
 
               multiply[c][d] = sum;                          // After Multiplication & Addition place it at its respective place
               sum = 0;
            }
         }
 
         System.out.println("Product of entered matrices:-");
 
         for ( c = 0 ; c < m ; c++ )
         {
            for ( d = 0 ; d < q ; d++ )
               System.out.print(multiply[c][d]+"\t");         // Final Results in matrix form using 2 for loops
 
            System.out.print("\n");
         }
      }
   }
}






























