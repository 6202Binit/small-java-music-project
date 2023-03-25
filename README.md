# small-java-music-project
In this project i have play music using p , reset music using r , stop music using s , quit using q . Its a simple small project it makes using learning period of java
import java.io.File;
import java.io.IOException;
import java.util.Scanner;

import javax.sound.sampled.AudioInputStream;
import javax.sound.sampled.AudioSystem;
import javax.sound.sampled.Clip;
import javax.sound.sampled.LineUnavailableException;
import javax.sound.sampled.UnsupportedAudioFileException;

public class audio{
    public static void main(String[]args) throws UnsupportedAudioFileException,IOException,LinkageError, LineUnavailableException{
        Scanner sc = new Scanner(System.in);
        File file = new File("music.wav");
        AudioInputStream audio = AudioSystem.getAudioInputStream(file);
        Clip clip = AudioSystem.getClip();
        clip.open(audio);
        String response = "";
        while(!response.equals('Q')){
            System.out.println("P = play , S = stop ,R = reset, Q = quit");
            System.out.println("enter your choic");
             response = sc.next();
            response = response.toUpperCase();
            switch(response){
                case("P"):clip.start();
                break;
                case("S"):clip.stop();;
                break;
                case("R"):clip.setMicrosecondPosition(0);
                break;
                case("Q"):clip.close();
                default:System.out.println("not response");
            }
        }
    }
}
