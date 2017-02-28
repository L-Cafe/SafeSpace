# Ideas for presence detection

There are multiple ways to detect presence, each with their own advantages and and shortcomings.

## Passive Infrarred Sensor

It's probably the most common presence sensor, and it's installed everywhere due to its low price and versatility.

### Advantages

- Typically have a wide field of view, so a single sensor can cover an entire room.
- Can be designed to ignore pets.
- Compact.

### Disadvantages

- Must be carefully placed away from heat sources such as heating systems.
- Must avoid windows, to avoid reflections from cars and other windows from overloading the sensor.
- Calibrating them is somewhat difficult.
- Might not respond well to quick movements.

## Ultrasonic transcievers

With a technology similar to sonar, these devices emit high frequency soundwaves with their special speaker, and listen for the echo with their microphone. These frequencies range from 18 kHz to 75 kHz, and are outside normal human hearing range.

### Advantages

- Are not affected by heat, light, or the optical properties of an object.
- Can also distance with relative accuracy.
- Well tested in automotive environments such as car parking sensors.

### Disadvantages 

- Must be placed perpendicularly to a hard, flat surface to receive adequate sound echo.
- Loud noises can trigger false alarms, such as the ones produced by relief valves.
- Since this technology measures the time between one burst of sound and the return of its echo, it has a much slower response rate than other technologies because it needs to stop transmitting, start measuring the time, and then get the signal back to be able to tell the distance. This delay is typically 0.1 seconds, so not very worrying in most cases.
- Ultrasonic sensors have a minimum sensing distance.
- Could disturb pets such as dogs.
- Low density targets, like cloth, absorb soundwaves and might not return them, producing inacurate results.

## Image-based motion detection

This kind of detection is generally present in most IP cams, and smartphone monitoring apps. It can also be found on some children monitors and webcam software for computers.

### Advantages

- Since it's images, it can go from really low quality with cheap cameras, to high quality using high FPS and high resolution sensors.
- It's possible, and relatively easy, to perform facial recognition using widely available libraries such as OpenCV.
- It's probably the easiest to set up because we can obtain a realtime video feed while setting up the camera.
- Ignore zones can be set up so the camera doesn't pick up activity in certain areas of the image, in the case, for example, the camera is picking part of the outside street.
- It can be configured so the system records a video every time movement is captured, or it could take pictures and send realtime alerts, as proof.

### Disadvantages

- It's the solution that requires the most processing power, because images must be analyzed continuously, and therefore, is the one that consumes the most electricity. This also means it cannot be implemented directly on an Arduino and could require something like a Raspberry Pi or a server to process the pictures.
- Is affected by light.
- Unless the camera has infrared capabilities (and an infrared lamp is placed in the field of view, which isn't cheap), the camera won't see anything if there's no light. Alternatively, a lamp could be installed to illuminate the room permanently, but this is very expensive electricity wise.

## Light beams/arrays

These kind of sensors are found in parking garages, to avoid the door from closing if there's a car passing. It doesn't need to be visible, infrared frequencies can be used.

### Advantages

- Very simple mechanism: Light is emitted from a device. If the other device receives light, then it's safe to determine nothing is between both devices.

## Laser rangefinder