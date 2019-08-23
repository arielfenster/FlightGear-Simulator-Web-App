# FlightGear Simulator Web App
A web application that is used to display the position of the aircraft in real time.

### Installing 
* Download and install the simulator on your computer- https://www.flightgear.org/download/
* Add the  generic_small.xml file to the /data/Protocol directory where you installed the simulator
* Config the following settings in the 'Settings' tab in the simulator:
```
--telnet=socket,in,10,127.0.0.1,5402,tcp
--generic=socket,out,10,127.0.0.1,5400,tcp,generic_small
```
![simulator-settings-config](https://user-images.githubusercontent.com/45856261/58368127-4a489680-7ef1-11e9-81ca-b17badca7f8e.PNG)

This will open two communication sockets - 'in' where you send commands to the simulator, and 'out' where you receive data from it.

### Preparing to lift off
a. First, you may need to adjust the time in the simulator from nighttime to daytime in order to see clearly.
Click on the Environment tab in the toolbar shown below, and click on Time Settings. Adjust the time to your liking.

![Toolbar](https://user-images.githubusercontent.com/45856261/63440757-1241e880-c439-11e9-9623-ed96e7eae199.PNG)

b. Next, in order to help you speed things up and bypass the take-off procedures, click on the Cessna C172P tab, and click on Autostart. This will start the engine and prepare the aircraft to lift off.

## Displaying the position
Run the application. Your default internet browser will open will the address 'localhost:xxx', where 'xxx' is a number. There are four of requestes you can perform which we will cover. The type of request is dependent on its format:

### Default view
Here you can see the map where the positions will be pinned: 
![empty map](https://user-images.githubusercontent.com/45856261/63607935-56b9b980-c5dc-11e9-8353-4bc0ceaeec64.PNG)

To view the map, type in the following request in the address bar:
```
localhost:xxx/display/id
```
change the id variable to any value you wish.

### Single point
In this request you ask the simulator for the current position of the aircraft. The outcome will result in a single point on the map:

![single point](https://user-images.githubusercontent.com/45856261/63608172-fb3bfb80-c5dc-11e9-87df-79e2cd8aa5a3.PNG)

To achieve this, type in the following request:
```
localhost:xxx/display/ip/port
```
where ip is the IP of the computer that the simulator is installed on, and port is the port number corresponds to the 'in' socket you configured above.
Each time you wish to view this outcome, you will have to refresh the page and send another request.

### Continuous points
But what if you don't want to keep refreshing the 

