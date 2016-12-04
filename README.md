#java-define-Thread-demo

两种方式创建一个线程：
- 继承 `Thread` 类
- 实现 `Runnable` 接口

覆盖 `run` 方法，调用 `Thread` 类的`start`方法启动线程。

```java
class ThreadByExtend extends Thread {

    @Override
    public void run() {
        for (int i = 0; i < 100; i++) {
            System.out.print("*");
        }
    }
}

class ThreadByImplement implements Runnable {

    @Override
    public void run() {
        for (int i = 0; i < 100; i++) {
            System.out.print("!");
        }
    }
}

public class DefineThread {
    public static void main(String[] args) {
        //线程就绪
        ThreadByExtend t1 = new ThreadByExtend();
        ThreadByImplement t2 = new ThreadByImplement();
        //线程启动
        t1.start();
        new Thread(t2).start();
        System.out.println("主线程over");
    }
}
```