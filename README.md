# MYSchoolTracker
Demo- Note- To see the tracking feature first need to do register and enter user information and school name for the demo of our product, we have used Divine Child High School, India- Surat

The inspiration behind Project/What led to this project?

We noticed that many school closures during the earlier parts of this year and notice the various attempts to reopen the schools has led to many issues such as confusion of when schools are entering and existing public schools. That for many children who are not participating in distance learning, there can be a sense of fear and worry that the new procedures being acted upon in schools can lead to confusion and bad coordination between new students and school officials.

Short/Brief Description

My School Tracker is a website application that allows parents to know when a child is safely inside campus areas when attending school. It keeps track when their child enters and exits a certain perimeter noted by the school or another organization. It could be set up for other locations such as libraries, other educational centers/buildings, and popular public spaces. Its main function is to let parents know when a child is inside or outside the school campus in a designated perimeter’s radius.

What is the purpose of your project?

The purpose of this project is to help parents know when their children are either inside or outside a school’s campus. This application was created in order to assist parents to know, with the consent of the child, where their children are during, and after school. It is a project aiming towards reducing stress levels in parents who want to know where their children are, and how to help practice safe behaviors during this pandemic.

How does your project give a positive impact on society? Benefits?

Helping people know if their child is at school during these difficult times helps relieve their stress. During this pandemic, there is a constant need to practice safe behavior such as social distancing and that requires separation from adults and children. By having geofences set up and note when children enter and exit school campuses, parents can know where a child is currently when schools are open or closed. My School Tracker works in tangent with the practices of school administrations and officials in order to help limit the spread of the virus.

SDK & API Information
Used Google API for everything:

https://developers.google.com/maps/documentation/javascript/examples/marker-labels
https://developers.google.com/maps/documentation/geocoding/start
First we get the coordinates for the school address reigstered to the user account
Then we show the school on the map and draw a radius around it
We then show all the children on the map and based on if they are inside or outside the radius we show them on the screen as green (safe) or red (bad)
NOTE: The child location is randomly generated every time the page is loaded or a child is added to simulate children moving around since we did not have time to implement actual tracking
MAP, RADIUS & LOCATION API
To display the map we made use of Google Cloud Services and the API's they provide. Google provides a script to include in the page, once the script is included and loaded it looks for a callback method which you specify in the script URL. That callback method (a local JavaScript method in our case called myMap) is called and then creates the new map instance, sets the focus point of the map and sets the radius. We also used the Google API to convert the school address to coordinates which the map uses. We then add a red radius around that location on the map using the Google SDK.

CHILDREN LOCATION & ALERT
Once a parent adds a new child this information is appended to the "children" property of the specific user in the users database (as mentioned earlier, we use PouchDB for this). This data is then added to the on screen table using standard JavaSctipt and HTML5 functionality. We use mathematical functions to calculate the direct/straight distance between the child and the school. If this distance is more than the radius we know the child is outside the allowed radius. NOTE: Since we didn't have time to create actual child location tracking functionality, every time a new child is added or when the page is refreshed, the location of the children is randomly generated somewhere close to the school. Some will be in the allowed radius and others will not be. This is to simulate the children moving around.

For the alerts, we again used standard JavaScript and HTML5 functionality to color the row of the child red if the distance from the school is more than the allowed radius or green if the child is within the safe zone. We also append an appropriate message in the distance column.
