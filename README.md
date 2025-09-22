# TELLO-DRONE-PYTHON-PROJECT-
This project demonstrates basic control of the DJI Tello Drone using python. 
# Code
import time
from djitellopy import Tello

# Create Tello object
tello = Tello()

try:
    # Connect to the drone
    tello.connect()
    print(f"Battery: {tello.get_battery()}%")

    # Takeoff
    tello.takeoff()
    time.sleep(2)  # hover for 2 seconds

    # Move forward 100 cm
    tello.move_forward(100)
    time.sleep(1)

    # Rotate clockwise 90 degrees
    tello.rotate_clockwise(90)
    time.sleep(1)

    # Land safely
    tello.land()

except Exception as e:
    print("Error:", e)
    try:
        tello.land()
    except:
        pass

finally:
    tello.end()
