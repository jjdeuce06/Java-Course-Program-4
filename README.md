# Java-Course-Program-4
## Program Outline
This program was designed to create a working frame using AWT methods presented in class. The program opens window that contains
  1. Two labels - one named speed and one named size
  2. A scrollbar labeled speed
  3. Four buttons - run, pause, circle, square, and quit
The program initializes a ball object that will bounce around the screen while running and will stop while pausing. The ball can be resized, sped up or slowed down, paused, have a tail, and be a square

## Implementation
This program uses WindowListener, ComponentListener, ActionListener, AdjustmentListener, and Runnable

### Main method
Begins an instance of the Bounce class

### Bounce Class
Program begins by manually position everything that will be on the frame, since it is a null layout manager. After this a new thread name thethread is initialized as well as a Objc object named obj. Labels for the scrollbars are created and then both the scrollbars are initialized as well as the buttons. Boolean values named runobj, Timepause, and start are declared

#### Constructor
Begins with two statements to use a null layout of frame and to make it visible using setVisible(true).

Then a call to the MakeSheet() function is made to determine sizes for sheet
A try/catch statement for a call to the initComponents() function comes next.
The start boolean is set to false, and calls to the SizeScreen() function and start() function end the constructor.

#### MakeSheet()
We set the value to the Inset object named I to the value returned by the getInsets() function
ScreenWidth and ScreenHeight is calculated with new Inset values
A call to setSize() is made with parameters WinWidth and WinHeight
CENTER, BUTTONW, BUTTONS are all reinitialized with new values
A call to setBackground() with the parameter Color.LIGHT_GRAY is made
ScrollBarW value is calculated

#### initComponents()
Booleans Timepause and runob set to true
Buttons are intiialized accordingly
Scrollbars are initialized accordingly
All elements are add to the frame
Listeners are added to objects
A call to setPreferredSize(new Dimension(WIDTH, HEIGHT)) is made
A call to setMinimumSize(getPrefferedSize()) is made
A call to setBounds(WinLeft, WinTop, WIDTH, HEIGHT) is made to size and position the frame
validate() called to validate the layout

#### SizeScreen()
Buttons are positioned on the frame
Scrollbars are positioned on the frame
Scrollbars are sized accordingly
Buttons are sized accordingly

#### start()
Check if thethread is null
  -if it is, initialize thethread to a new thread and start the thread
call the setx, sety, and repaint functions of the Obj object class

#### run()
  while the runobj boolean is true
    delay the thread for 1 millisecond, catch the InterruptedException error.
    Check if Timepause is false, if it is, set start to true and delay the thread again with       the value from the speed scrollbar.
    Call the move() function and the Obj.repaint() function


#### stop()
  set runObj to false, interrupt the thread, remove listeners, dispose window, and exit

#### move method
  Call the find max and min methods for the Obj object's x and y values.
  Check if the object's next position is outside any of the values and reverse the direction     accordingly.
  repaint() call at the end.

#### adjustmentValueChanged
  create integer named TS.
  get the scrollbar that triggered the function
  if it was the speed scrollbar, update the speed
  if it was the object size scrollbar, update the obejct size 

#### componentResized()
  Get current width and height, set screen width and height accordingly using insets
  Resize the object canvas and find new max and min values
  get current x and y values, check if object is still on the screen and redraw if need be
  recalculate and resize components with calls to MakeSheet() and SizeScreen()
    
    

