# Installation #

This page will show how easy it is to incorporate the DateSlider into your application. The procedure is very similar to the default DatePicker Dialog:

```
public class SimpleDemo extends Activity {
    
static final int DEFAULTDATESELECTOR_ID = 0;
	
	private TextView dateText;
	
    @Override
    public void onCreate(Bundle savedInstanceState) {
    	// load and initialise the Activity
        super.onCreate(savedInstanceState);
        setContentView(R.layout.main);
        dateText = (TextView) this.findViewById(R.id.selectedDateLabel);
        Button defaultButton = (Button) this.findViewById(R.id.defaultDateSelectButton);
        
        // set up a listener for when the button is pressed 
        defaultButton.setOnClickListener(new OnClickListener() {
			public void onClick(View arg0) {
				// call the internal showDialog method using the predefined ID
				showDialog(DEFAULTDATESELECTOR_ID);
			}        	
        });
    }

    // define the listener which is called once a user selected the date.
    private DateSlider.OnDateSetListener mDateSetListener =
        new DateSlider.OnDateSetListener() {
            public void onDateSet(DateSlider view, Calendar selectedDate) {
            	// update the dateText view with the corresponding date
                dateText.setText(String.format("The chosen date:%n%te. %tB %tY", selectedDate, selectedDate, selectedDate));
            }
    };    
    
    @Override
    protected Dialog onCreateDialog(int id) {
    	// this method is called after invoking 'showDialog' for the first time
    	// here we initiate the corresponding DateSlideSelector and return the dialog to its caller

    	// get todays date and the time
        final Calendar c = Calendar.getInstance();
        switch (id) {
        case DEFAULTDATESELECTOR_ID:
            return new DefaultDateSlider(this,mDateSetListener,c);
        }
        return null;
    }
}
```

As already said, it is very similar to the DatePicker. The main difference is that you communicate with the DateSlider via Calendar instances. This enables all the DateSlider implementations to use the same interface no matter which time units need to be selected.


## Requirements ##

To make this example work you need the following files from the `src/` folder:
  * `DateSlider.java`
  * `ScrollLayout.java`
  * `TimeView.java`
  * `DefaultViewer.java`

and those from the `res/` folder:
  * `slider_nosnap.png`
  * `dateslider.xml`
  * `dialogtitle.xml`
  * `simplemain.xml`
  * `scroller.xml`

## Important Note ##

There is a bug in the Android tools (http://code.google.com/p/android/issues/detail?id=9656). The problem is that if you declare a styleable in a library project, you cannot refer to those custom xml attributes from your main project until the Android folks fix the tools. The workaround is to copy the `<declare-styleable>` block from DateSlider's attrs.xml into an attrs.xml in your main application project.

That should get it building

- Thanks a lot to Ben Demboski for this work around!