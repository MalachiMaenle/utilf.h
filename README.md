# utilf.h

## Instructions for adding to your c++ program:
  1) download the file util.h
  2) place the file within the same folder as your c++ program file
  3) put ```#include "utilf.h"``` in your header declarations section

## Features:
- Text formatting
- wait(int milliseconds);
- blip();
- blip(int delay <in milliseconds>);

## Clear text formatting:
- clearf

## Disable text display:
- disable

## Color formatting for text:
- black
- red
- green
- yellow
- blue
- magenta
- cyan
- white
- bright_black
- bright_red
- bright_green
- bright_yellow
- bright_blue
- bright_magenta
- bright_cyan
- bright_white

## Formatting for text background:
- bg_black
- bg_red
- bg_green
- bg_yellow
- bg_blue
- bg_magenta
- bg_cyan
- bg_white
- bg_bright_black
- bg_bright_red
- bg_bright_green
- bg_bright_yellow
- bg_bright_blue
- bg_bright_magenta
- bg_bright_cyan
- bg_bright_white

## Other text formatting options:
- bold - bolds the text
- subtitle - lightens the text slightly
- italic - italicises the text
- underline - underlines the text
- contrast - swaps text and text background colors
- invisible - makes the text invisible

## Using text formatting examples:
```cpp
- cout << bright_cyan "Hello World" << endl;
- cout << bright_cyan << "Hello World" << endl;
- cout << bright_cyan underline "Hello World" << endl;
- cout << bright_cyan underline << "Hello World" << endl;
- cout << bright_cyan "Hello World" clear << endl;
- cout << bright_cyan << "Hello World" << clear << endl;
```
To format text, list the formatting you want the text to have before the text, and to clear formatting use "clear".\
You can create a combination of formats by defining them: ```#define <name> <list of formats>```\
Ex: ```#define caution bold bright_red bg_bright_yellow underline```

Another Thing you can do with the color formatting allows you to turn the entire background a single color.\
By using the short code below, you can change the entire console/terminal background cyan:\
```cpp
cout << bg_cyan; //sets all text after this to have a cyan background - (until formatting is cleared)
wait(1); //A short 1 millisecond pause from this header file to make this weird trick work 100% of the time
system("clear"); //clears the entire console screen but also colors it the background color currently in use
```

## Cursor movement:
Use similar to how you would use the colors in cout statements.\
Examples: ```cout << cursor_left;``` ```cout << backspace << "E";```
- cursor_up - Moves the console cursor up one line.
- cursor_down - Moves the console cursor down one line.
- cursor_right - Moves the console cursor right one character.
- cursor_left - Moves the console cursor left one character.

## Keyboard input:
- <variablename>.startInput(); - starts custom keyInput
- <variablename>.stopInput(); - stops custom keybInput - (returns to standard input)
- <variablename>.input(); - function to update the pressed key - (updates the <variablename>.key char variable to inputted key)
- <variablename>.key - key inputted, can be used in if statements,switches,etc. to detirmine the effect of pressed keys.

## KeyBoard input notes:
- Useful for movement in games!
- uparrow keycode: 65
- downarrow keycode: 66
- rightarrow keycode: 67
- leftarrow keycode: 68

## Keyboard input example:
```cpp
#include <iostream>
#include <string>
#include "utilf.h"

using namespace std;

int main() {
  string word;
  
  //showing standard input before keyInput starts
  cout << "Enter a word: ";
  cin >> word;
  cout << "Your word is: " << word << endl;
  cout << "keyInput started! Press q to stop!" << endl;
    
  getKey.startInput(); //starts custom input
  
  while(getKey.key != 'q') { //runs loop until Q is pressed
    getKey.input(); //updates getKey.key to most recent input
    switch(getKey.key) { //switch statement to detirmine what key was pressed and what action it will do
      case 'w': //if W was pressed
        cout << "you went up!" << endl;
        break;
      case 's': //if S was pressed
        cout << "you went down!" << endl;
        break;
      case 'd': //if D was pressed
        cout << "you went right!" << endl;
        break;
      case 'a': //if A was pressed
        cout << "you went left!" << endl;
        break;
    }
  }
  getKey.stopInput(); //returns to standard input
  
  //showing standard input after keyInput has stopped
  cout << "Enter a new word: ";
  cin >> word;
  cout << "Your new word is: " << word;
  
  return 0;
}
```

## Other functions:
- wait(int milliseconds); - a delay that pauses ththe current thread in the program for the specified number of milliseconds
- blip(); - a short blip sound
- blip(int delay <in milliseconds>); - a short blip sound that plays after the delay specified in milliseconds
