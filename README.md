# circle big and small art;
package cember.buyume.kuculme.animasyon;
import java.applet.Applet;
import java.awt.Color;
import java.awt.Graphics;
import java.util.Random;
import java.util.logging.Level;
import java.util.logging.Logger;
import static javafx.scene.paint.Color.color;
import static javafx.scene.paint.Color.color;

public class CEMBERBUYUMEKUCULMEANİMASYON extends Applet implements Runnable {
int x,y;
int yaricap;
int yaricapp=30;
public void init(){
    setSize(500,600);
   x=getWidth()/2;
   y=getHeight()/2;
Thread tt=new Thread((Runnable) this); 

tt.start();

}
    public void paint(Graphics g){
       int red=(int)Math.round(Math.random()*255);
        int blue=(int)Math.round(Math.random()*255);
         int green=(int)Math.round(Math.random()*255);
        Color c=new Color(red,blue,green);
  g.setColor(c);
   g.fillOval(400+x,300, yaricap,yaricap);
   yaricap+=yaricapp;
   x-=yaricapp;y-=yaricapp;
    }
    public void run(){ 
  while(true){ try {
      Thread.sleep(180);
     
  if(x<=0&&y<=0){

  yaricapp*=-1;
  
  }
   if(x>getWidth()/2&&y>getWidth()/2){
  
yaricapp*=-1;
  }
   else  if(yaricapp==0){
  yaricapp*=+1;
  }
 
  repaint();
     
  } catch (InterruptedException ex) {
          Logger.getLogger(CEMBERBUYUMEKUCULMEANİMASYON.class.getName()).log(Level.SEVERE, null, ex);
      }
    }
 
}}
