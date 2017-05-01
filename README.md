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

1. Usnig only a P control resulted in oscillating movements of the car around the centreline. The higher the p-error coefficient is, more oscillations will result.  

<html>
    <video width="99%" height="540" autoplay loop muted>
        <source src="/videos/vid-p0.75-i0.0-d0.0.mp4" type="video/mp4">
    </video>
</html>

2. A combination of P and D control can result in a relatively smooth ride. It appears the amuont of the drift is not significant, and the combinatino of the P and D works. In order to eliminate/reduce the amount of oscillation around the centerline, the amount of the D coefficient should be one order of magnitude larger than the P coefficient.  
3. Fianlly adding the I control component will result in a smoother ride. However, the I-error coefficient should be very small relative to P-coefficient; otherwise, the car will go off track.  
