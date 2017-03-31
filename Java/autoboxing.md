`
public class Toy {
    public static void main(String[] args){
        double a=Double.NaN;
        double b=Double.NaN;
        Double x=new Double(Double.NaN);
        Double y=new Double(Double.NaN);
        System.out.println(a==b); //false
        System.out.println(x.equals(y));//true

        a=0.0;
        b=-0.0;
        x=new Double(0.0);
        y=new Double(-0.0);
        System.out.println(a==b);//true
        System.out.println(x.equals(y));//false
    }
}
`