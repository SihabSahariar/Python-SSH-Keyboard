# Python-SSH-Keyboard
A resource to use keyboard stroke from anywhere!

# Why sshkeyboard?
The pynput module monitors the Linux input subsystem, which is for input devices attached to your local machine (keyboards, joysticks, mice, etc). 
Keystrokes received over an ssh connection aren't handled by the input subsystem, because they're not coming from an input device -- they're just data coming over a network connection.
Rather than relying on pynput, your code should just be monitoring standard input for keystrokes. This will work both when running locally and when running over an ssh connection
Fortunately, the [sshkeyboard](https://sshkeyboard.readthedocs.io/) module will handle much of this for you; take a look at this example code:

```
# pip install sshkeyboard
from sshkeyboard import listen_keyboard
def press(key):
    if key == "up":
        print("up pressed")
    elif key == "down":
        print("down pressed")
    elif key == "left":
        print("left pressed")
    elif key == "right":
        print("right pressed")

listen_keyboard(on_press=press)
```
