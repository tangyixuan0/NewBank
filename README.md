# NewBank
编写一个银行帐户类，并编写测试类，测试功能。银行帐户类的构成包括私有 成员变量（帐户名称、密码、帐户余额）


import java.util.Scanner;

public class Bank {

    //键盘输入
    Scanner reader = new Scanner(System.in);


    //申明账号，密码
    private int ZhangHao,MiMa;



    public void setZhangHao(int zhangHao) {
        ZhangHao = zhangHao;
    }
    public int getZhangHao() {
        return ZhangHao;
    }



    public void setMiMa(int miMa) {
        MiMa = miMa;
    }
    public int getMiMa() {
        return MiMa;
    }

    //创建账号密码
    public void chuangjian( ) {
        System.out.println("请输入您新建的账号：");
        ZhangHao = reader.nextInt();
        System.out.println("请输入您新建的密码：");
        MiMa = reader.nextInt();
        System.out.println("创建成功！");
    }


    //申明余额
    int money;

    //存钱
    public int cun(){
        System.out.println("输入您要存入的金额：");
        int a = reader.nextInt();
        money = money + a;
        System.out.println("存款成功！");
        return money;
    }
    //取钱
    public int qu(){
        System.out.println("输入您要取出的金额：");
        int a = reader.nextInt();
        money = money - a;
        System.out.println("取款成功！");
        return money;
    }
    //查询
    public void chaxun(){
        System.out.println("您的余额为："+money);
    }
}



class Test2 {
    public static void main(String[] args) {


        //创建bank对象
        Bank bank = new Bank();
        //调用方法chuangjian
        bank.chuangjian();


        //打印输出
        System.out.println("请输入您的账号：");
        //键盘输入
        Scanner reader = new Scanner(System.in);


        //申明、赋值Zhanghao1
        int Zhanghao1 = reader.nextInt();
        //打印输出
        System.out.println("请输入您的密码：");
        //申明、赋值Mima1
        int Mima1 = reader.nextInt();


        //判断账号密码是否输入正确
        if (Zhanghao1 == bank.getZhangHao() & Mima1== bank.getMiMa()){

            //倘若正确
            boolean x = true;
            //do-while语句
            do{
                //打印输出
                System.out.println("验证成功"+"\n"+"输入操作：1.取款 2.存款 3.查询 4.退出");
                //键盘录入赋值c,用户的选择
                int c = reader.nextInt();

                //switch开关语句
                switch (c){
                    case 1 :{
                        //调用方法qu()
                        bank.qu();
                        //换行
                        System.out.println();
                        //continue语句，继续下一次循环
                        continue;
                    }
                    case 2 :{
                        //调用方法cun()
                        bank.cun();
                        System.out.println();
                        continue;
                    }
                    case 3 :{
                        //调用方法chaxun()
                        bank.chaxun();
                        System.out.println();
                        continue;
                    }
                    case 4 :{
                        //把false赋给x，break语句终止本次循环，同时X=false时，不继续循环
                        x = false; break;
                    }

                }
            }while (x == true);//x==true时继续执行循环体

            }else{//倘若错误，打印输出
                System.out.println("验证失败，账号或密码错误！");
        }

    }

}

