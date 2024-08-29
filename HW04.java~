// NOTE: Once you understand how this sample code works,
//       you will want to delete/change most of it. :)

import java.util.*;

class HW04 extends App {
    ArrayList<ArrayList<ArrayList<Vector2>>> animation;
    int frameCount = 0;
///////////////////////////////////////////////////////////////////    
    
///////////////////////////////////////////////////////////////////    
    void setup() {
        animation = new ArrayList<>();
        animation.add(new ArrayList<ArrayList<Vector2>>());
    }
///////////////////////////////////////////////////////////////////
    
///////////////////////////////////////////////////////////////////
    void loop() {
        ///// EVERYTHING before Flipping
        {   
            ///// Adding strokes
            if (mousePressed){
                animation.get(frameCount).add(new ArrayList<Vector2>());
            }
            if(mouseHeld){
                animation.get(frameCount).get(animation.get(frameCount).size() - 1).add(mousePosition);
            }
            /////// Drawing strokes
            for (int i = 0; i < animation.get(frameCount).size(); ++i) {
                for (int j = 0; j < animation.get(frameCount).get(i).size() - 1; j++){
                    drawLine(animation.get(frameCount).get(i).get(j), animation.get(frameCount).get(i).get(j +1), Vector3.blue);
                }
            }
            ///// Flip frame horizontally by 'X'
            if (keyPressed('X')) { 
                for (int i = 0; i < animation.get(frameCount).size(); ++i) {
                    for (int j = 0; j < animation.get(frameCount).get(i).size(); j++){
                        animation.get(frameCount).get(i).get(j).x = (- animation.get(frameCount).get(i).get(j).x);
                    }
                }
            }
            ///// Flip frame horizontally by 'Y'
            if (keyPressed('Y')) { 
                for (int i = 0; i < animation.get(frameCount).size(); ++i) {
                    for (int j = 0; j < animation.get(frameCount).get(i).size(); j++){
                        animation.get(frameCount).get(i).get(j).y = (- animation.get(frameCount).get(i).get(j).y);
                    }
                }
            }
        }
        ///// NEW Frame
        if (keyPressed('S') && !keyToggled('P')) {
            animation.add(new ArrayList<ArrayList<Vector2>>());
            
            for(int i = animation.size() - 1; i > frameCount + 1; i--){
                animation.set(i, animation.get(i-1));
            }
            frameCount++;
            animation.set(frameCount, new ArrayList<ArrayList<Vector2>>());
            
        }
        ///// Play and Pause
        if (keyToggled('P')) {
            frameCount = ++frameCount % animation.size();
            long start = System.currentTimeMillis();
            while (System.currentTimeMillis() - start < 300){}
        }
        if (keyPressed('.')) {frameCount = Math.floorMod(++frameCount, animation.size());}
        if (keyPressed(',')) {frameCount = Math.floorMod(--frameCount, animation.size());}
    }
//////////////////////////////////////////////////////////////////    
    
//////////////////////////////////////////////////////////////////    
    public static void main(String[] arguments) {
        App app = new HW04();
        app.setWindowBackgroundColor(1.0, 1.0, 1.0);
        app.setWindowSizeInWorldUnits(8.0, 8.0);
        app.setWindowCenterInWorldUnits(0.0, 0.0);
        app.setWindowHeightInPixels(512);
        app.setWindowTopLeftCornerInPixels(64, 64);
        app.run();
    }
    
}