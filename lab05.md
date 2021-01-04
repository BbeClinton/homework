## 1. 介绍“自顶向下，逐步求精”的编程方法
  自顶而下是一种逐步求精的设计程序的过程和方法。对要完成的任务进行分解，先对最高层次中的问题进行定义、设计、编程和测试，而将其中未解决的问题作为一个子任务放到下一层次中去解决。这样逐层、逐个地进行定义、设计、编程和测试，直到所有层次上的问题均由实用程序来解决，就能设计出具有层次结构的程序。
  
  所以，首先要求你必须对你所设计的系统有一个全面的理解.然后从顶层开始,连续地逐层向下分解,分解到所有的模块都能用具体的程序运行，这样就能逻辑地构造整个系统。

## 2. 用“自顶向下，逐步求精”解读洗衣机的程序设计
- 1)首先确定洗衣机程序的大致框架

      READ pattern
      water_in() 
      motor_run()
      water_out()  
      dehydrate()
      END FOR
      ring()  
      halt(success)

- 2）逐个完善子程序
 
      water_in(){
      water_in_switch(open)  
      WHILE get_water_volume() < heigh_water_volume  
      END WHILE
      water_in_switch(close)  
      }
      water_out(){
      water_out_switch(open)  
      WHILE get_water_volume() > low_water_volume  
      END WHILE
      water_out_switch(close)
      }
      motor_run(){
      FOR motor_run_time = 1 to 10  
      motor_run(right)  
      wait(5000)
      motor_run(stop)   
      wait(2000)
      motor_run(left)   
      wait(5000)
      motor_run(stop)   
      wait(2000)
      END FOR
      }
      dehydrate(){
      motor_run(right)  
      wait(10000)
      motor_run(stop)   
      }
      wait(time){
      justnow=time_counter();
      WHILE(time_counter()<justnow+time)
      END WHILE
      }
      ring(){
      ring(on)  //响鸣2s
      wait(2000)
      ring(off)
      }

  - 3)优化，调整程序
      
        wait(time){
        now = time_counter();
        WHILE(time_counter()<now+time)
        END WHILE
        }
         water_in(volume,timeout){
         now = time_counter();
         water_in switch(open)
         WHILE get_water_volume() < volume 
          IF time_counter() > timeout
          THEN halt(failure)
          ENDIF
          ENDWHILE
           water_in switch(close)
        }
        water_out(timeout)
        water_out_switch(open)  
        WHILE get_water_volume() > low_water_volume 
        END WHILE
        water_out_switch(close)
        wait(timeout)

        以上是对等待时间，注水，排水子程序的优化，使之更易理解和修改维护。

        