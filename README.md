# ACTAM-Project


<p align="center">
    <img src="images/logo.png" alt="alt text">
</p>

<p align="center">
    At this link you can try the app:
  <a href="https://annafusari.github.io/itsNotGarageBand/">click and try</a>
</p>


## Group:

- ####  Chiara Auriemma &nbsp;([@ChiaraAuriemma](https://github.com/ChiaraAuriemma))<br> 10722613&nbsp;&nbsp; chiara.auriemma@mail.polimi.it

- ####  Enrico Torres &nbsp;([@enry1897](https://github.com/enry1897))<br> 10712642&nbsp;&nbsp; enrico.torres@mail.polimi.it

- ####  Anna Fusari &nbsp;([@AnnaFusari](https://github.com/AnnaFusari))<br> 10561236&nbsp;&nbsp; anna.fusari@mail.polimi.it

<br>

<p align="center">
  <a href="https://youtu.be/9ChYAzdux1c">
    <img src="https://github.com/ChiaraAuriemma/ACTM-Project/blob/main/deliveries/images/Screen3.png" alt="Watch the video" width="800" style="border-radius: 8px;">
  </a>
</p>

<br>

### About the project
The aim of the project is to create a DAW that is intuitive and simple to use for those approaching music production for the first time.
The software gives you the ability to do multiple things:
1. The ability to choose from different instruments (piano, drums, guitar, and bass) and play them with the application.
2. Ability to play all the described instruments through a MIDI keyboard.
3. Ability to manage the volume and more of the instruments
4. Possibility to record all the instruments and play the recorded material
6. The capability to record your voice using the PC microphone and play it back
7. Ability to determine the length of recordings based on the number of measures you want to record.
8. Capacity to delete recordings and instruments at will.
9. Ability to loop the tracks.
10. Metronome

<br>
<div  align="center">
<img width="80%" src="https://github.com/ChiaraAuriemma/ACTM-Project/blob/main/deliveries/images/Screen1.png" align="center" />
</div>
<br><br>
<div  align="center">
<img width="80%" src="https://github.com/ChiaraAuriemma/ACTM-Project/blob/main/deliveries/images/Screen2.png" align="center" />
</div>
<br>

### How to use the app
- **Record an instrument:** press the rec button, then open the instrument that you want to play clicking on the image and start to play whatever you want. Have fun! Remember that the recording start when you click on the first note
- **How to record more bars:** Before recording, change the number of bars of the instrument
- **Record the voice:** press the rec button, then click on one of the empty squares of the voice , start talking and click again on the square when you are done
- **Loop:** press the loop button and click on the record that you want to loop. When you want to stop it , remember that the loop button must be active. To stop click again on the record
- **MIDI:** You can plug the MIDI in any moment but when you want to use it rembember to open the instrument. If you want to feel like a drummer use the pads!!
 
### Model-View-Controller
To structure the project we used the model-view-controller pattern. All three are js files in the project. In the model we save the application information, we note the current status of the operations, which instruments i have created and the management of records. For instruments and recordings we have also created classes to simplify management.

The controller is responsible for understanding what needs to be done and which functions to call at a given moment. HTML elements have associated functions within the controller.

The view takes care of the graphic elements and the creation of html elements. In fact, we have only one html page that changes dynamically thanks to javascript.

All the other js files refer to the creation of musical instruments or other things which for greater clarity we have separated from the rest.

We also have many css files that take care of the styling of the graphic elements.

### Technologies and libraries
- To make the instruments play, we chose a set of sounds personally by exploring available online **samples** and loading them into our project. For their management, we used the **Howler** library. We created lists consisting of Howl objects, which are easy to handle given the methods already available for them.
- For voice recording, we used the **MediaRecorder** object, which provides functionality to easily record media. Specifically, it allows starting the recording, configuring it to save the incoming stream, and then, upon stopping, saving the entire content into the model. What we do is creating a **blob**, which is transformed into an **AudioElement**.
- For instrument recording, we chose to save the played **notes** along with their **timestamps**. This allows us to replay them when the user decides to listen to the recording. It seemed like the most practical and resource-efficient approach.
- Regarding MIDI, we handle the arrival of **midimessages**, analyze the received message, and redirect the content to the same functions used to play the virtual instruments of the application. In order to do so, we used the methods of the **Web MIDI API**.

### Project-related challenges
The biggest difficulty of the project was its heterogeneity. A DAW allows you to carry out various operations, and we chose the ones that seemed most significant to us. The project contained many elements, but we tried to have an as modular approach as possible. Instead of writing dedicated code for each instrument, we created classes and shared as much code as possible for each one. Regarding recording, we adopted a different approach for instruments compared to voice because it seemed more useful to save information related to notes rather than a much bulkier audio file in terms of memory.The difficulty with MIDI was establishing the correspondence between sounds and keys, but once resolved, we were able to limit the code by reusing functions like noteon and noteoff, which were already used elsewhere to play the sounds. In particular we observe that differt parts of the MIDI keyboard sometimes are mapped in different ways depending on the device. The main problem was with the pads, so we decided to let the pads play every time we don't have to play the keyboard.

