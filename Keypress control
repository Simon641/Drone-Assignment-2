from djitellopy import Tello
import KeyPressModule as kp
from time import sleep

kp.init()
tello = Tello()
tello.connect()
print(tello.get_battery())


def getKeyboardInput():
    lr, fb, ud, yv = 0, 0, 0, 0
    speed = 50

    if kp.getKey("LEFT"):
        lr = -speed
        # Left movement
    elif kp.getKey("RIGHT"):
        lr = speed
        # Right movement

    if kp.getKey("UP"):
        fb = speed
        # forward movement
    elif kp.getKey("DOWN"):
        fb = -speed
        # Backwards movement

    if kp.getKey("w"):
        ud = speed
        # Up movement
    elif kp.getKey("s"):
        ud = -speed
        # Down movement

    if kp.getKey("d"):
        yv = speed
        # Rotate right
    elif kp.getKey("a"):
        yv = -speed
        # Rotate left

    if kp.getKey("q"):
        tello.land()
        # land drone
    if kp.getKey("e"):
        tello.takeoff()
        # takeoff drone

    return [lr, fb, ud, yv]


while True:
    vals = getKeyboardInput()
    tello.send_rc_control(vals[0], vals[1], vals[2], vals[3])
    sleep(0.05)
