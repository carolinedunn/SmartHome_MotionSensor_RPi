# SmartHome_MotionSensor_RPi
This project combines a Raspberry Pi with a motion sensor to control a smart home device with IFTTT

Materials:

Assumptions:
- Working knowledge of how to setup a fresh Raspberry Pi with the Raspbian operating system.
- Understanding how the Raspberry Pi GPIO works
- How to boot up a Raspberry Pi.
- Previously setup a smart plug that is currently active and connected to your home or office Wifi network.

# Step 1: Setup Raspbian OS
Download and install Raspbian OS

# Step 2: Hardware Assembly
- Insert your MicroSD card with Raspbian into your Raspberry Pi.
- Connect your motion sensor to your Raspberry Pi. If you are using a Raspberry Pi Zero, you may need to solder header pins.
  - Connect the Ground pin of your motion sensor to GPIO pin 6 of your Raspberry Pi
  - Connect the OUT pin of your motion sensor to GPIO pin 11 of your Raspberry Pi
  - Connect the VCC pin of your motion sensor to GPIO pin 2 of your Raspberry Pi
- Attach a mouse, keyboard, and monitor to your Raspberry Pi.
- Power on your Pi.

# Step 3: Setup IFTTT

In this step, you'll setup your IFTTT Webhook
- Go to: https://ifttt.com/
 If you don't already have an account with IFTTT, create one. It is free and does not require a credit card.
- Login to IFTTT
- Click the "Get More" button in the top right
- Click the '+' button to the right of "Make Your Own Applets from scratch."
- Click "This"
- Search for "webhook" and click the "Webhook icon"
- Click "Receive a web request"
- Enter "motion_detected" and click the "Create trigger" button
- Click "That"
- Search for your smart plug vendor or smart plug app and click the appropriate icon.
- Connect your smart plug with IFTTT. Enter your login and password for your smart home plug and authorize the connection with IFTTT.
- Click on your desired action.
- Configure (if necessary) and click "Create Action"
- Click the IFTTT logo in the top left and search for "webhook" in sthe "Search Filters" field.
- Click Webhook
- Click "Documentation" and leave that web browser session open for the next step.

# Step 4: Software Installation

Open a Terminal and run the following commands

```
sudo apt-get update
sudo apt-get upgrade
mkdir ifttt
cd ifttt
wget
sudo nano iftttpir.py
```
- Go back to your IFTTT webpage and copy the key
- Paste IFTTT key into line 46. 
For example, r = requests.post('https://maker.ifttt.com/trigger/motion_detected/with/key/KXXXXXXXXXXXXXXA6pE', params={"value1":"none","value2":"none","value3":"none"})
- Ctrl-X
- Y to save

Now let's try running the code!
```sudo python3 iftttpir.py```

Now move your hand in front of your motion sensor and see if it works. If it doesn't work, retrace your steps.




  
