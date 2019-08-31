# How to connect GPIOzero to the MeArm

This can be tried in a python3 repl (terminal session) then put into a file.
You must have followed the [setting up](preparing_the_pi.md) steps first.

    $ python3
    >>> from gpiozero.pins.pigpio import PiGPIOFactory
    >>> gpiozero.Device.factory = PiGPIOFactory()
    >>> base = gpiozero.Servo(4)
    
Python may grumble here, stuff about Fallback. Ignore it.

Set up the other servos:

    >>> gripper = gpiozero.Servo(10)
    >>> right = gpiozero.Servo(17)
    >>> left = gpiozero.Servo(22)
    
## Interacting with the servos

These are using the [Servo](https://gpiozero.readthedocs.io/en/stable/api_output.html#servo) object from GPIOZero. 

You can set the middle with:

    >>> base.mid()

This should set the rotation of the arm (shoulder) to the middle.
And go to extents with:

    >>> base.min()
    >>> base.max()
    
You can also set .value to vary this:

    >>> base.value = 0.7
    
This should be a value between -1.0 and 1.0 with 0 being the middle.
Left and right should be elbow and shoulder angles. I need to check which way up they are.
