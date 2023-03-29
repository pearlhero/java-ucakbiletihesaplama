# java-ucakbiletihesaplama
java-ucakbiletihesaplama

import java.util.Scanner;
public class Main {
public static void main(String[] args){
 int km, age, tripType;
 double normalPrice, ageDiscount, tripTypeDiscount;

Scanner input = new Scanner(System.in);

System.out.print("Mesafeyi giriniz (km cinsinden): ");
    km = input.nextInt();
System.out.print("Yaşınızı giriniz : ");
    age = input.nextInt();
System.out.print("Yolculuk tipinizi giriniz (Tek-gidiş = 1 Gidiş-dönüş = 2) : ");
    tripType = input.nextInt();

if ((km > 0) && (age > 0) && (tripType==1 || tripType==2)){
normalPrice = km * 0.10;
if (age < 12){
    ageDiscount = normalPrice * 0.5;
    normalPrice -= ageDiscount;
}else if ((age > 11) && (age < 25)){
    ageDiscount = normalPrice * 0.1;
    normalPrice -= ageDiscount;
} else if (age >= 65) {
    ageDiscount = normalPrice * 0.3;
    normalPrice -= ageDiscount;
} else {
    ageDiscount = 0;
}if (tripType == 2){
    tripTypeDiscount = normalPrice * 0.2;
    normalPrice = (normalPrice - tripTypeDiscount) * 2;
}
System.out.println("Toplam tutar : " + normalPrice + "TL");

}else {
System.out.println("Hatalı bilgi girdiniz. Lütfen yeniden deneyiniz.  ");
}
}

}
