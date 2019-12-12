---
title: "Testing and Debugging our Game"
language: "en"
previous: "dataPath.html"
next: "hardwarePreparation.html"
---
<center><h1>Testing and Debugging our Game!</h1></center>

Now that we have finished our data path and our FSM, it's time to test it out and make sure that our FSM is working properly, which is very important to find out as we have 2 FSM and we might encounter synchronizing issue (will explain more later). So....
<center>
<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTtBFfrvBikl4Uz4s5nvL2RF3a4OiqLgAAziP0HXuaGYwE-fj0B&s">
</center>

---

## Testing Button Inputs
To start the testing, first we tested the button inputs for +, -, and x by connecting a button and a pair of seven segment to show the player's current number as +, -, and x will change them.

We realized that one press of the button registers as multiple button presses, so we decided to add in button conditioner and edge detector for each button to reduce it as much as we can even though there will still be some occasion where it registers multiple times.

Inside ```.clk(clk) {...}``` :

```
edge_detector edgeAdd1 (#RISE(1), #FALL(0));
button_conditioner condAdd1;
```

Inside ```always {...}``` :
```
condAdd1.in = add1;
edgeAdd1.in = condAdd1.out;
```

---

## Testing Shifting 'Character'
Now that we know the buttons are working properly, we decided to test out whether the 'character' in each lane will shift properly or not. We tested with 1 lane first.

We tested and it was correct, we tested getting another problem correct after the flag in one lane is captured to see which lane will be updated or not. The correct one would be the next lane that is shifted (as the previous one's flag is already captured)

<center>
Everything was working and everything was correct!
</center>

<center>
<img src="https://media.tenor.com/images/012b7efc748fea5a3a8987df5b13b671/tenor.gif">
</center>

---

## Testing Multiplayer Mode
After everything is proven to be working correctly, we want to test out the dynamic of having 2 player play this game. We built the controllers for the buttons and seven segments, and used some leds on breadboard to show the lanes. Two of us played (competitively of course), and it was fun for us! We had noticed a few bug that we immediately try to fix.
|Bugs|Solution|
|-|-|
|After the game ended, if we start the game again, the lane that will be "shifted" is the 3rd lane which is the last lane|We realized we had forgotten to "reset" the value in the register that saves the "current lane", so we had that fixed|
|The character's position in each lane was not reset properly (the "characters" does not go back to position one)|We had forgotten to implement this too, so we added it in >.<|

---
And now that we are sure everything works, here comes hardware.
<center><img src="https://media.giphy.com/media/KdB8MsRiiUXUA/giphy.gif"></center>