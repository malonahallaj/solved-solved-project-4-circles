Download Link: https://assignmentchef.com/product/solved-solved-project-4-circles
<br>
In a prior lab exercise, we had to complete the code to test whether two circles, each having a user-defined radius and a fixed center point lying along the same horizontal line, are disjoint, overlapping, or mutually contained.

We desire to develop a more general solution to the problem â€“ an object oriented solution.

Begin by considering that the word circle is a noun, hence we want to have a Circle class.

What describes a circle? Its position and radius.

Lastly, what behaviors does a circle exhibit? Besides various accessor and mutator methods, we want to know if â€˜thisâ€&#x2122; circle is disjoint, contained within, or overlapping with â€˜anotherâ€&#x2122; circle. Additionally, a circle can change â€“ expand or contract via its radius. It can also â€˜moveâ€&#x2122; to another position.

Create two classes, Circle and Position.

The Position class has instance data for its coordinate, x and y, along the x axis and yaxis, respectively. It has the following methods:

1. A constructor taking two parameters to establish the x and y coordinate.2. Accessor methods, getX and getY for x and y, respectively.3. A move method taking two parameters, x and y.4. A distance method taking as a parameter another Position object, p. It returns the absolute distance from p.5. A toString method that returns a string for the x,y coordinates enclosed in parentheses, e.g., â€œ(-1.5,2.0)â€.

The Circle class has a instance data a Position object and its radius. It has the following methods:

1. A Constructor taking three parameters: its radius, x position and y position.2. Two accessor method: getRadius returns its radius and getPosition that returns its Position object.3. A mutator method, setRadius that changes the radius of the circle.4. A move method taking two parameters, x and y.5. A distance method taking as a parameter another Circle object, c. It returns the absolute distance of their centroidsfrom c.6. A boolean method, isDisjoint, taking as a parameter another Circle object, c. It returns true if this circle is disjoint from c.7. A boolean method, contains, taking as a parameter another Circle object, c. It returns true if the circle cis contained within this circle.8. A boolean method, overlaps, taking as a parameter another Circle object, c. It returns true if this circle overlaps with c.9. A toString method that returns a string for the radius and x,y coordinates enclosed in parentheses, e.g., â€œ4.3 @ (-1.5,2.0)â€.

The logic for determining whether they are disjoint, mutually contained, or overlapping is basically the same as for the prior lab â€“ but simpler!

If the distance between two circles, d, is less than the sum of their radii, r1and r2, then they overlap. If d is greater than or equal to the sum of their radiithey are disjoint. A circle, c2, is contained within circle c1 if (d + r2) is less than or equal to r1.

The following can be used to test the Circleand Position classes. Comments show the expected result.

“`javapublic class CircleTester{public static void main(String[] args){Circle c1 = new Circle(1, 0, 0);display(“c1: ” + c1.toString());Circle c2 = new Circle(2, 1, 1);display(“c2: ” + c2.toString());Circle c3 = new Circle(1, 2, 0);display(“c3: ” + c3.toString());

display(“c1 &amp; c2 disjoint? ” + c1.isDisJoint(c2)); //falsedisplay(“c1 &amp; c3 disjoint? ” + c1.isDisJoint(c3)); //truedisplay(“c2 &amp; c3 disjoint? ” + c2.isDisJoint(c3)); //false

display(“c1 &amp; c2 overlap? ” + c1.overlaps(c2)); //truedisplay(“c1 &amp; c3 overlap? ” + c1.overlaps(c3)); //falsedisplay(“c2 &amp; c3 overlap? ” + c2.overlaps(c3)); //true

display(“c1 contains c2? ” + c1.contains(c2)); //falsedisplay(“c2 contains c1? ” + c2.contains(c1)); //falsedisplay(“c1 contains c3? ” + c1.contains(c3)); //false

display(“c3 contains c1? ” + c3.contains(c1)); //falsedisplay(“c2 contains c3? ” + c2.contains(c3)); //falsedisplay(“c3 contains c2? ” + c3.contains(c2)); //false

Circle c4 = new Circle(2.5, 1, 0);display(“c4: ” + c4.toString());display(“c1 contains c4? ” + c1.contains(c4)); //falsedisplay(“c4 contains c1? ” + c4.contains(c1)); //true}

public static void display(String message){System.out.println(message);}}“`