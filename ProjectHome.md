# Dateslider for Android #

## Welcome ##
The Dateslider is a framework for a range of date picker widgets based on the principle of sliding bars. This results in a very intuitive and enhanced user experience.

## How does it look like? ##
Here are some sample implementations:

---

![http://blog.codeus.net/wp-content/uploads/2011/06/ds-default.png](http://blog.codeus.net/wp-content/uploads/2011/06/ds-default.png)
![http://blog.codeus.net/wp-content/uploads/2011/06/ds-alternative.png](http://blog.codeus.net/wp-content/uploads/2011/06/ds-alternative.png)


_two implementations of representing a date picker_

---

![http://blog.codeus.net/wp-content/uploads/2011/06/ds-time.png](http://blog.codeus.net/wp-content/uploads/2011/06/ds-time.png)
![http://blog.codeus.net/wp-content/uploads/2011/06/ds-month-year.png](http://blog.codeus.net/wp-content/uploads/2011/06/ds-month-year.png)


_an implementation of a time picker and a slider which only contains month and year_

---

![http://blog.codeus.net/wp-content/uploads/2011/06/ds-datetime.png](http://blog.codeus.net/wp-content/uploads/2011/06/ds-datetime.png)
![http://blog.codeus.net/wp-content/uploads/2011/06/ds-costum.png](http://blog.codeus.net/wp-content/uploads/2011/06/ds-costum.png)


_fully customisable, i.e. get a slider that contains a great variety of information or change the look and feel as you like_

---

What you can't see is the slider's behaviour while scrolling - both bars are connected to each other. That is, if the lower bar is moved, the upper bar will move a bit as well. And when the upper bar is scrolled, then the lower bar will move such that both bars will always correspond. This looks nice and feels nice.

## Updates ##

we switched to github. The latest code can be found here:
https://github.com/bendemboski/DateSlider
however, the downloads on this google code project represent the latest stable release.

### Version 1.2 ###
  * major refactoring of the code base by Ben Demboski
  * easy customisation of the minute interval in the time slider
  * enabling setting a minimum and/or a maximum date

![http://blog.codeus.net/wp-content/uploads/2011/06/ds-default-limit.png](http://blog.codeus.net/wp-content/uploads/2011/06/ds-default-limit.png)

_example of a limit - no more scrolling past the 6 July_