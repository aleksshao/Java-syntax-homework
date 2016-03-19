# Java-syntax-homework - 19.03.2016 





public class CalculateExpression {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        double a = input.nextDouble();
        double b = input.nextDouble();
        double c = input.nextDouble();

        double f1 = Math.pow((Math.pow(a,2) + Math.pow(b,2)) / (Math.pow(a,2) - Math.pow(b,2)),((a + b + c)/Math.sqrt(c)));
        double f2 = Math.pow((Math.pow(a,2) + Math.pow(b,2)) - (Math.pow(c,3)),(a - b));
        double diff = ((f1+f2)/2) - ((a+b+c)/3);

        System.out.printf("F1 result: %.2f; " + "F2 result: %.2f; " + "Diff: %.2f", f1, f2, diff);
    }
}


public class CharacterMultiplier {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        String firstString = input.nextLine();
        String secondString = input.nextLine();
        System.out.println(totalOfSum(firstString, secondString));
    }
    static int totalOfSum(String ch1, String ch2) {
        int sumOfCh = 0;
        if (ch1.length() > ch2.length() || ch1.length() < ch2.length()) {
            for (int i = 0; i < ch2.length() ; i++) {
                sumOfCh+= ch1.charAt(i) * ch2.charAt(i);
            }
            for (int i = ch2.length() ; i < ch1.length() ; i++) {
                sumOfCh+= ch1.charAt(i);
            }
            for (int i = 0; i < ch1.length() ; i++) {
                sumOfCh+= ch1.charAt(i) * ch2.charAt(i);
            }
            for (int i = ch1.length() ; i < ch2.length() ; i++) {
                sumOfCh+= ch2.charAt(i);
            }
        }else{
            for (int i = 0; i < ch1.length(); i++) {
                sumOfCh += ch1.charAt(i) * ch2.charAt(i);
            }
        }
        return sumOfCh;
    }
}



public class ConvertFromBase7ToDecimal {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        int base = input.nextInt();
        String number = input.next();

        int decimalValue = 0;
        int step = 0;
        for (int i = number.length() - 1; i >= 0; i--) {
            char ch = number.charAt(i);
            //System.out.println(c);
            int chValue = Character.digit(ch, base);
            //System.out.println(cValue);
            decimalValue = decimalValue + (chValue * (int) Math.pow(base, step));
            step++;
        }
        System.out.println(decimalValue);

    }
}




public class ConvertFromDecimalSystemTobase7 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        int number = input.nextInt();
        int base = input.nextInt();
        int remainder;
        String result = " ";
        while(number != 0){
            remainder = number % base;
            result = remainder + result;
            number = number / base;
        }
        System.out.println(result);
    }
}

//https://www.youtube.com/watch?v=yxIGZ9wST_4




public class ExtractWords {
        public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        String s = input.nextLine();

        Pattern pat = Pattern.compile((""));
        Matcher matcher = pat.matcher(s);
        String onlyAlphabet = s.replaceAll("[!\"#$%&'()*+,-./:;<=>?@^_`{|}~0123456789]"," ");
        System.out.println(onlyAlphabet);
    }
}



public class FormattingNumbers {
        public static void main(String[] args) {
            Scanner input = new Scanner(System.in);

            int a = input.nextInt();
            float b = input.nextFloat();
            float c = input.nextFloat();

            String temp = Integer.toBinaryString(a);
            int temp1 = Integer.parseInt(temp);

            System.out.printf("|%X" + "    " + "|0%09d|" + "     " + "%.2f" + "|%.3f|", a, temp1, b, c);


        }
}




public class HitTheTarget {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        int digit = input.nextInt();

        for (int i = 1; i <= 20; i ++) {
            for (int j = 1; j <= 20; j++) {
                if ((i + j == digit)){
                    System.out.printf("%d + %d = %d\n", i, j, digit);
                }else if((i - j)== digit){
                    System.out.printf("%d - %d = %d\n", i, j, digit);
                }

            }
        }
    }
}



public class OddAndEvenPairs {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        String[] numbers = input.nextLine().split(" ");

        if (numbers.length % 2 != 0) {
            System.out.println("Invalid length");
        } else {
            for (int i = 0; i < numbers.length-1; i += 2) {
                int firstNumber = Integer.parseInt(numbers[i]);
                int secondNumber = Integer.parseInt(numbers[i + 1]);

                if (firstNumber % 2 == 0 && secondNumber % 2 == 0) {
                    System.out.printf("%d, %d -> both are even\n", firstNumber, secondNumber);
                }else if (firstNumber % 2 != 0 && secondNumber % 2 != 0) {
                    System.out.printf("%d, %d -> both are odd\n", firstNumber, secondNumber);
                }else {
                    System.out.printf("%d, %d -> different\n", firstNumber, secondNumber);
                }

            }

        }
    }
}



public class RandomizeNumbersFromNToM {
    public static void main(String[] args) {

        Scanner input = new Scanner(System.in);
        int n = input.nextInt();
        int m = input.nextInt();
        if (n > m) {
            for (int i = 0; i < (n - m)+ 1; i++) {
                System.out.print(" " + (int) ((Math.random() * (m - n) + n)));
            }
        } else {
            for (int i = 0; i < (m - n)+ 1; i++) {
                System.out.print(" " + (int) ((Math.random() * (m - n) + n)));
            }


        }
    }

}




public class RectangleArea {

    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        int a = input.nextInt();
        int b = input.nextInt();

        int rectangleArea = a * b;
        System.out.println(rectangleArea);
    }
}




public class StartsAndEndsWithCapitalLetter {
            public static void main(String[] args) {
            Scanner input = new Scanner(System.in);
            String s = input.nextLine();

            Pattern pat = Pattern.compile(("\\b[A-Z]+[A-Za-z]*[A-Z]+\\b"));
            Matcher matcher = pat.matcher(s);

                while(matcher.find()){
                    System.out.print(matcher.group() + " ");
                }

        }
    }
    
    
  

public class TriangleArea {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        int aX =  input.nextInt();
        int aY =  input.nextInt();
        int bX =  input.nextInt();
        int bY =  input.nextInt();
        int cX =  input.nextInt();
        int cY =  input.nextInt();

        int triangleArea = (aX * (bY - cY) + bX * (cY - aY) + cX * (aY - bY)) / 2;
        System.out.println(Math.abs(triangleArea));
    }
}
