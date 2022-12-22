# Dynamic-Traffic-Project
It was a government funded traffic management project that I worked on and used Python to control all the hardware devices and also developed a time switching algorithm 
to calculate the waiting time for each based on the traffic density for each lane and also based on priority scheduling algorithm.
This System dynamically manages the traffic on a 4 Lane intersection by Detecting the maximum vehicles from a particular lane and then updating the
timers of the lane itself and other lanes.The Tech Stack that we used for developing this system were , Raspbian OS , Python for Detecting the Vehicles 
and counting the number of detected vehicles and according to the count updating the Traffic Timer.I Used Deep Learning and Computer Vision for Vehicle Detection and
used RPI.GPIO library for interfacing this detection + time calculation algorithm with the Relay Modules,etc.

Description of the Code :
(1)Traffic Swithching New.py : This file consists of the Code where I have developed the Logic for calculating the time that would be required for each lane based on 
     traffic count and also based on the priority for each lane.
      Priority Scheduling is an algorithm where we are assigning priority for each lane.
      a.Initially we are extracting the count of the vehicles using Vehicle_1.py where I have used Transfer Learning for training a Vehicle Detection Model and used the
         architechture of YoloV3 Model for the same.
         
      b.After extracting the Vehicle count for each Lane we are taking the Lane with maximum vehicle count and based on the traffic density in that Lane we calculating
        the Traffic Timer for that Lane.
        
      c.Now once we Updated timer for a particular lane then we are adding +5 to the Priority List for that Lane whose timer we just updated.
      
      d.We are subtracting -5 for the lanes whose timers are not updated.
      
      e.So this is what Priority Scheduling does it maintains a priority list for the Lanes and if a particular Lane lets say has a prority value of -10 for example then 
        that lane would be selected and the timer for that lane would be calculated based on its traffic density.
        
      f.Due to this Lanes with Very Low traffic density does not have to wait for a very long time and Basically gives fair priority to each lane.
      
      g.Main purpose of the Priority Scheduling is to give fair priority to each lane.
      
NOTE:Do watch the Demo video for getting an Idea how we have implemented a Basic Prototype with Raspberry Pi , Relays , Traffic Lights and Videos for Traffic Vehicles for 2 Lane intersection.
