import java.util.Scanner;

class Main {

  public static void Lat(int f){
    String s = f + "";
    System.out.print("\nДанное число в арабском исчеслении выглядит так:\t");
    int z, l = 0, d, e, k = s.length();
    if(f == 1000){ System.out.print("\nM");}
    else{
      if(k == 3) { e = f % 1000 / 100; }//трехзначные
      else{e = 0;}
      if(e == 0){}
      else if(e > 4 && e < 9){e = e - 5; System.out.print("D");}
      else if(e == 4){System.out.print("CD");}
      else if(e == 9){System.out.print("CM");}
      if(e < 4){for(int i = 0; i < e; i++) {System.out.print("C");} }

      if(k >= 2) { d = f % 100 / 10; }//двузначные
      else{ d = 0;}
      if(d == 0){}
      else if(d > 4 && d < 9){d = d - 5; System.out.print("L");}
      else if(d == 4){System.out.print("XL");}
      else if(d == 9){System.out.print("XC");}
      if(d < 4){for(int i = 0; i < d; i++) {System.out.print("X");} }

      z = f % 10;//однозначные
      if(z == 0){}
      else if (z == 4){System.out.print("IV");}
      else if(z > 4 && z < 9){z = z - 5; System.out.print("V");}
      else if(z == 9){System.out.print("IX");}
      if(z <= 3){ for(int i = 0; i < z; i++) {System.out.print("I");} }
    }
  }

  public static void Pal(int z){
    String a = z + "", s = "";
    if(a.length() == 1){ System.out.println("\nДанное число однозначное.\n");}
    else{
      for(int i = a.length()-1; i > -1; i--) {s += a.charAt(i);}
      int ss =  Integer.parseInt(s);
      int aa =  Integer.parseInt(a);
      if(ss == aa){ System.out.println("\n Данное число является палиндромом.\n");}
      else{ System.out.println("Данное число не является палиндромом.");}
    }
  }

  public static void main(String[] args) {

    Scanner sc = new Scanner(System.in);
    System.out.println("\nЗадание №1. Создать функцию которая производит преобразование римских цифр в арабские.");
    int f;
    do{
      System.out.print("\nВведите число: ");
      f = sc.nextInt();
    }while(f < 0 || f > 1000);
    Lat(f);
    System.out.println("\n\nЗадание №2. Определить является ли вводимое число палиндромом.");
    int z;
    do{
      System.out.print("\nВведите число: ");
      z = sc.nextInt();
    }while(z < 0 || z > 999999);
    Pal(z);
  }
}