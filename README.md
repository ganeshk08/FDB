# FDB
package foodfactory;

import java.util.Scanner;


 interface Food
    {
        public String getType();
    }
class Cake implements Food
    {
        @Override
        public String getType() {
            return "Someone oredered a dessert";
        }
    }
    
    class Pizza implements Food
    {                        
        @Override
        public String getType() {
//            System.out.println("Someone oredered a Fast Food");
            return "Someone oredered a Fast Food";
        }
    } 

class Ffactory
{   
    /**
     *
     * @param order
     * @return
     */
    public Food getFood(String order)
    {
        if(order == null)
        {
            return null;            
        }
        else if(order.equalsIgnoreCase("cake"))
        {
//            System.out.println("Someone oredered dessert");
            Food f= new Cake();
            return f;          
        }
        else if(order.equalsIgnoreCase("pizza"))
        {
//            System.out.println("Someone oredered a Fast Food");
            Food f= new Pizza();
            return f;
        }
        else
        {
            return null;
        }
    }
            
//    public static void main(String[] args) 
//    {   
//        Scanner sc=new Scanner(System.in);
//        
//        Foodfactory ff= new Foodfactory();    
//        System.out.println("Please choose order pizza or cake");
//        String ord = sc.next();
//        ff.getFood(ord);
//    }
    
}
public class Foodfactory
{
    public static void main(String[] args) 
    {   
        Scanner sc=new Scanner(System.in);
        
        Ffactory ff= new Ffactory();
                
        System.out.println("Please choose order pizza or cake");
        String ord = sc.next();
        Food fu= ff.getFood(ord);
        System.out.println(fu.getClass());
        System.out.println(fu.getType());        
    }
}
