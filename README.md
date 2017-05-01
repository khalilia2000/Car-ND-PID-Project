# CarND-Controls-PID
Self-Driving Car Engineer Nanodegree Program

---

## Dependencies

* cmake >= 3.5
 * All OSes: [click here for installation instructions](https://cmake.org/install/)
* make >= 4.1
  * Linux: make is installed by default on most Linux distros
  * Mac: [install Xcode command line tools to get make](https://developer.apple.com/xcode/features/)
  * Windows: [Click here for installation instructions](http://gnuwin32.sourceforge.net/packages/make.htm)
* gcc/g++ >= 5.4
  * Linux: gcc / g++ is installed by default on most Linux distros
  * Mac: same deal as make - [install Xcode command line tools]((https://developer.apple.com/xcode/features/)
  * Windows: recommend using [MinGW](http://www.mingw.org/)
* [uWebSockets](https://github.com/uWebSockets/uWebSockets) == 0.13, but the master branch will probably work just fine
  * Follow the instructions in the [uWebSockets README](https://github.com/uWebSockets/uWebSockets/blob/master/README.md) to get setup for your platform. You can download the zip of the appropriate version from the [releases page](https://github.com/uWebSockets/uWebSockets/releases). Here's a link to the [v0.13 zip](https://github.com/uWebSockets/uWebSockets/archive/v0.13.0.zip).
  * If you run OSX and have homebrew installed you can just run the ./install-mac.sh script to install this
* Simulator. You can download these from the [project intro page](https://github.com/udacity/CarND-PID-Control-Project/releases) in the classroom.

## Basic Build Instructions

Provided that all dependencies are alredy installed and linked properly:  

1. Clone this repo.
2. Make a build directory: `mkdir build && cd build`
3. Compile: `cmake .. && make`
4. Run it: `./pid`. 

## Reflections

The coefficients for the PID controller were set using manual adjusting starting only by setting the P coefficient. Then adding the D coefficient, and then adding the I coefficient. Of course for each coefficient considered, there were lots of fine-tuning while keeping the previous coefficients constant. The following reflections are noted:

1. Usnig only a P control resulted in oscillating movements of the car around the centreline. The higher the p-error coefficient is, the sharper will be the return to the centerline. The following 2 videos show the behaviour of the car using P coefficients of 0.75 and 5.0.  A P coefficient of 0.75 was chosen as the best setting value:

[video-1 with coefficients: P=0.75, I=0.0, D=0.0](https://github.com/khalilia2000/Car-ND-PID-Project/blob/master/videos/vid-p0.75-i0.0-d0.0.mp4)

[video-2 with coefficients: P=5.0, I=0.0, D=0.0](https://github.com/khalilia2000/Car-ND-PID-Project/blob/master/videos/vid-p5.0-i0.0-d0.0.mp4)

2. The D coefficient should be an order of magnitude higher than the P coefficient. The following 2 videos show the behaviour of the car using D coefficients of 0.75 and 30.0 (both using a P coefficient of 0.75 as stated above). As can be noted from the videos, a D coefficient of 30.0 (along with P coefficient of 0.75) results in successful laps around track. A combination of P and D control can result in a relatively smooth ride, however, due to the drift being present in the car steering, once in a while the car sharply turns back towards the centerline. It appears the amuont of the drift is not significant though.  

[video-3 with coefficients: P=0.75, I=0.0, D=0.75](https://github.com/khalilia2000/Car-ND-PID-Project/blob/master/videos/vid-p0.75-i0.0-d0.75.mp4)

[video-4 with coefficients: P=0.75, I=0.0, D=30.0](https://github.com/khalilia2000/Car-ND-PID-Project/blob/master/videos/vid-p0.75-i0.0-d30.0.mp4)

3. Fianlly adding the I control component will result in a smoother ride. However, the I-error coefficient should be very small relative to P-coefficient; otherwise, the car will go off track.  
