# Point-Tracer
It was one of my projects with Java language in CS152 course. By running the program, a short animation of a pointer on the screen will be displayed which is creating a square and then a fancy shape.

/**
 * Project draws a square then a circle on circles then a creative shape
 * User should set length value to 6000 and speed to max
 * @author Behnoud Alaghband
 * @date September 19,2022
 */
public class PointTracer {

    /**
     * The main method covers all actions of this project
     *
     * @param args can always be ignored
     */
    public static void main(String[] args) {

        // Create new display object
        Display panel = new Display(6000, 3);

        //Draws line from center-top point to top-right corner.
        for (int x = 200; x <= 340; x++) {
            panel.drawNextPoint(x - 1, 40);
        }

        //Draws line from top-right corner to bottom-right corner.
        for (int y = 40; y <= 360; y++) {
            panel.drawNextPoint(340, y);
        }

        //Draws line from bottom-right corner to bottom-left corner.
        for (int x = 340; x >= 60; x = x - 1) {
            panel.drawNextPoint(x, 360);

        }

        //Draws line from bottom_left corner to top_left corner.
        for (int y = 360; y >= 40; y = y - 1) {
            panel.drawNextPoint(60, y);
        }

        //Draws line from top-left corner to top-center.
        for (var x = 60; x <= 200; x++) {
            panel.drawNextPoint(x, 40);
        }

        //Drawing circle on circle
        int centerX7 = 200;
        int centerY7 = 200;
        double degAng7 = 270;
        double radius7 = 160;
        //The main circle particulars
        while (degAng7 < 630) {
            double radAng7 = Math.toRadians(degAng7);
            double x7 = centerX7 + radius7 * Math.cos(radAng7);
            double y7 = centerY7 + radius7 * Math.sin(radAng7);
            degAng7 += 3;

            int centerX8 = (int) x7;
            int centerY8 = (int) y7;
            double degAng8 = 270;
            double radius8 = 30;
            //The Smaller circles particulars
            while (degAng8 < 630) {
                double radAng8 = Math.toRadians(degAng8);
                double x8 = centerX8 + radius8 * Math.cos(radAng8);
                double y8 = centerY8 + radius8 * Math.sin(radAng8);
                panel.drawNextPoint((int) x8, (int) y8);
                degAng8 += 3;
            }
            degAng7 += 2;

        }



        // Calculate center point
        int centerX = 200;
        int centerY = 200;
        // Calculate degree angle that changes the angle
        double degAng = 270;
        // Calculate the radius
        double radius = 160;
        double radius2 = 130;
        double radius4 = 100;

    // Draws a complete circle
            while (degAng < 630) {
                //Converts degree angel to radian
                double radAng = Math.toRadians(degAng);
                //Calculate the coordinates of every point on
                // the main circles
                double x = centerX + radius * Math.cos(radAng);
                double y = centerY + radius * Math.sin(radAng);
                double x2 = centerX + radius2 * Math.cos(radAng);
                double y2 = centerY + radius2 * Math.sin(radAng);
                double x3 = centerX + radius4 * Math.cos(radAng);
                double y3 = centerY + radius4 * Math.sin(radAng);


                //Calculate the centers of smaller circles on
                // the first main circle
                int centerX1 = (int) x;
                int centerY1 = (int) y;
                int centerX2 = (int) x2;
                int centerY2 = (int) y2;
                int centerX3 = (int) x3;
                int centerY3 = (int) y3;
                //The degree angle of the  smaller circles
                double degAng1 = 270;
                double degAng2 = 270;
                double degAng3 = 270;
                //The radius of the smaller circles
                double radius1 = 30;
                double radius3 = 25;
                double radius5 = 20;
                //loops for degree angle of smaller circles
                while (degAng1 < 630) {
                    double radAng1 = Math.toRadians(degAng1);
                    double x1 = centerX1 + radius1 * Math.cos(radAng1);
                    double y1 = centerY1 + radius1 * Math.sin(radAng1);
                    panel.drawNextPoint((int) x1, (int) y1);
                    degAng1 += 1;
                }
                //loops for degree angle of smaller circles
                while (degAng2 < 630) {
                    double radAng2 = Math.toRadians(degAng2);
                    double x1 = centerX2 + radius3 * Math.cos(radAng2);
                    double y1 = centerY2 + radius3 * Math.sin(radAng2);
                    panel.drawNextPoint((int) x1, (int) y1);
                    degAng2 += 1;
                }
                //loops for degree angle of smaller circles
                while (degAng3 < 630) {
                    double radAng3 = Math.toRadians(degAng3);
                    double x1 = centerX3 + radius5 * Math.cos(radAng3);
                    double y1 = centerY3 + radius5 * Math.sin(radAng3);
                    panel.drawNextPoint((int) x1, (int) y1);
                    degAng3 += 1;
                }
                //Distance of the smaller circles of the main circle
                degAng += 20;

            }


        }


    }
