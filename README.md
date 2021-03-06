# Interlock Demo
The goal of this project is to demonstrate a run-time monitor for verifying visual lane perception. There are four components: the sensor, controller, monitor, and actuator. The monitor detects flaws in the controller's perception and intervense when these flaws are detected. Docker is used to enforce isolation between components. This project was developed as a final project for 6.858. 

## Requirements
Must be using a working distribution of Linux and have docker and docker-compose installed.

## Usage
To use, run `docker-compose build` and `docker-compose up`. `docker-compose.yml` may need to be changed depending which system to run:
  * To run the untampered controller, no modification is needed. 
  * To run the controller that sends stale image data, change the controller service to build from `./controller_old`.
  * To run the controller that stops sending certificates after a while, change the controller service to build from `./controller_stops`.
  * To run the controller that tampers with the images, change the controller service to build from `./controller_wrong_image`.
  * To have the sensor feed the controller an image it cannot correctly identify lane lines in, change the sensor service to build from `./sensor_bad_photo`. 
