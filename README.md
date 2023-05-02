Download Link: https://assignmentchef.com/product/solved-cmpt381-assignment-1-widgets-and-events-in-android
<br>
In Part 1, you will build a basic interface with Android widgets, and will write event handlers to deal with user interaction on those widgets. In Part 2, you will build a custom widget class for a “range slider” that can be used in your program. This assignment will demonstrate your ability to use widgets and widget APIs, to handle basic user-interface events at the application level, and to implement basic widget controls in a custom class.

<h1>Part 1: An interface with basic widgets and events</h1>

NOTE: when the Android documentation talks about “widgets” it often means “app widgets” (the small controls that users can put on their home screens). This is not the kind of widget that is involved in this assignment – in 381, we will use “widget” to refer to a visual interaction component in a UI toolkit.

Build a simple interface with the Android widgets TextView, EditText, Switch button, and SeekBar (see picture at right). Your system simulates a Settings page for a hypothetical app, and should include:

<ul>

 <li>A TextView at the top of the screen with the text “Settings” in large font.</li>

 <li>A Switch button with the text “Allow Notifications” that can be turned on or off.</li>

 <li>A TextView (with text “Volume”) and a SeekBar that allows the user to set a value in the range 0-100.</li>

 <li>A TextView (with text “Telephone Number”) and an EditText that allows the user to enter a phone number.</li>

 <li>A multiline TextView that displays a summary of the settings, as shown in the picture. The summary is updated immediately whenever the Switch, SeekBar, or EditText are manipulated by the user.</li>

 <li>The rows of widgets in the interface should be organized vertically using a LinearLayout container (with orientation set to vertical); when a row involves more than one widget, use another LinearLayout container.</li>

 <li>You can use the Android interface designer to build your UI (or you can build it in code).</li>

</ul>

Handling events for the widgets in the UI:

<ul>

 <li>Android widgets typically use Listener interfaces to receive events. You will need to listen for changes to the Switch, the SeekBar, and the phone number’s EditText.</li>

 <li>For the SeekBar, use an OnSeekBarChangeListener.</li>

 <li>For the Switch, use an setOnCheckedChangeListener.</li>

 <li>For the EditText, use a TextChangedListener.</li>

 <li>How you wire together the widgets and the listeners is up to you (e.g., anonymous class, anonymous inner class, or implementing the listener interface in your MainActivity class)</li>

 <li>On any change, call a method that will create the summary string and put it into the summary TextView. Resources:</li>

 <li>The API documentation for all of the Android classes listed above: <u>https://developer.android.com/docs/</u></li>

 <li>Using Android Studio’s visual editor: <u>https://developer.android.com/studio/write/layout-editor</u></li>

 <li>Getting access to XML components from Java code: <u>https://developer.android.com/guide/topics/ui/declaringlayout</u> (see the example text “Button myButton = (Button) findViewById(R.id.my_button);”)</li>

 <li>Android event handling overview: <u>https://developer.android.com/guide/topics/ui/ui-events</u></li>

 <li><u>https://docs.oracle.com/javafx/2/ui_controls/slider.htm</u></li>

 <li>Tutorial for the JavaFX VBox: <u>http://www.javafxtutorials.com/tutorials/hboxvbox/</u></li>

 <li>Tutorial for JavaFX event handling: <u>https://docs.oracle.com/javafx/2/events/jfxpub-events.htm</u> (note that this tutorial does not cover events for Slider widgets)</li>

</ul>

<h1>Part 2: Adding a custom widget</h1>

Build a custom widget called a RangeSeek, which contains two SeekBar widgets and uses them in combination to allows the user to set a range (e.g., 20-80 as in the picture at right). Add your RangeSeek widget to the interface you built for Part 1, and update the event handling so that the range from the RangeSeek widget is shown in the summary.




Your implementation should meet the following requirements:

<ul>

 <li>The widget shows two SeekBar widgets stacked vertically. The left handle of the widget is on the top, and the right handle is on the bottom.</li>

 <li>RangeSeek widgets always use a scale of 0-100, and always use MATCH_PARENT for their horizontal layout parameter, and WRAP_CONTENT for the vertical parameter.</li>

 <li>The user can click and drag the handles of the two SeekBar widgets to set the left and right ends of the range.</li>

 <li>The left handle cannot pass the right handle, and the right cannot pass the left.</li>

 <li>Creation of the widget. RangeSeek’s constructor should take four values: o A Context (for passing on in constructors of the superclass and the individual SeekBar widgets)  o The int value of the initial left handle position o The int value of the initial right handle position

  <ul>

   <li>A MainActivity object for communicating event callbacks back to the parent  Implementation: o RangeSeek should extend class LinearLayout</li>

   <li>You should create two SeekBar objects and add event handlers to listen for changes (within the</li>

  </ul></li>

</ul>

RangeSeek class) o Whenever a change occurs, you should directly call method OnRangeSeekChanged() with the new left and right values. (You will have to write this method in your MainActivity class)

<ul>

 <li>You may wish to add getLeftValue() and getRightValue() methods to the RangeSeek class.</li>

</ul>

<ul>

 <li>Demo program. Add two RangeSeek widgets to the interface developed in part 1 (see example above). o NOTE: you may not simply build the functionality of a RangeSeek widget into your basic interface – you must create RangeSeek objects and add them to your layout container. If you do not build the RangeSeek as a widget class, you will not receive any marks for Part 2.

  <ul>

   <li>Whenever the range changes, immediately update the text summary in the main interface.</li>

  </ul></li>

</ul>

This assignment is to be done individually; each student will hand in an assignment.