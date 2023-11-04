# Intro

Во второй части проекты становятся немного сложнее (и интереснее). Изучив и попробовав на практике представленные материалы, ты научишься
1) Одновременно управлять множеством двигателей.
2) Собирать информацию о вращении двигателя с помощью датчиков.
3) Превращать вращательное движение вала мотора в линейное.
4) Контролировать поведение двигателя с помощью обратной связи.

# Моторы (часть вторая)

## Multiple motors

При подключении нескольких моторов усложняется логика управления: чтобы обеспечить плавность движения, необходимо своевременно передавать команды каждому из подключенных двигателей. 

[Stepper Motors and Arduino – The Ultimate Guide](
https://howtomechatronics.com/tutorials/arduino/stepper-motors-and-arduino-the-ultimate-guide/)

[Controlling 3 Stepper Motors with the AccelStepper Library for Arduino](
https://www.youtube.com/watch?app=desktop&v=QRCvC5xhJCw)

Можно выделить 2 подхода к одновременному управлению системой двигателей: блокирующий и неблокирующий. В первом случае двигателям назначаются целевые координаты, затем вызывается функция, которая обеспечивает движение к заданным параметрам, блокируя новые обращения до тех пор, пока не будет достигнута цель.

[Пример блокирующего управления](
https://github.com/swissbyte/AccelStepper/blob/master/examples/MultiStepper/MultiStepper.pde)

При неблокирующем управлении продолжительная процедура движения вала двигателя от начального положения к цели разбивается на множество коротких шагов, которые можно исполнить за короткий промежуток времени. Затем эти короткие шаги постепенно исполняются в основном цикле программе вместе с другими операциями.

[Пример неблокирующего управления](https://github.com/swissbyte/AccelStepper/blob/master/examples/MultipleSteppers/MultipleSteppers.pde)

Другие примеры:

[AccelStepper examples](https://github.com/swissbyte/AccelStepper/tree/master/examples)

### CNC Shield V3

Типовой задачей является подключение набора двигателей для управления несколькими осями станка. Для этого можно воспользоваться платой расширения для Arduino:

[Multiple motors using an Arduino CNC Shield V3](
https://www.aranacorp.com/en/using-an-arduino-cnc-shield-v3/)

[How to control a Stepper Motor with Arduino Motor Shield Rev3](
https://www.makerguides.com/arduino-motor-shield-stepper-motor-tutorial/)

[Coordinated stepper motor control (arduino)](
https://www.youtube.com/watch?v=fHAO7SW-SZI)


## Motor + encoder

Энкодер - специальный датчик, позволяющий отслеживать угол поворота вала двигателя. Они бывают разных типов, но для работы с шаговыми двигателями удобно пользоваться магнитным энкодером AS5600.  

[AS5600 magnetic position encoder - best encoder for stepper motors](
https://www.youtube.com/watch?v=yvrpIYc9Ll8)

[Measuring speed and position using the AS5600 magnetic encoder](
https://www.youtube.com/watch?v=NY8RllFVrZg)

Несколько моторов с энкодерами через мультиплексор I2C

[MINIQ BG6300 milling table with stepper motors and AS5600 encoder](
https://curiousscientist.tech/blog/miniq-bg6300-milling-table-with-stepper-motors-and-as5600-encoder)

## Servomotor II

В первой части мы пробовали управлять сервомоторами, но при желании можно собрать и собственную систему обратной связи.  

[How to make a REAL servo out of any motor. Multi-loop control](https://www.youtube.com/watch?v=yFH8key-t_M)

[Build a Custom Servo Motor with a DC Motor](https://dronebotworkshop.com/custom-servo-motor/)

## Simple robots

Если реализовыва хотя бы по одному проекту из каждой главы, то к настоящему моменту будет достаточно знаний для того, чтобы приступить к сборке отдельных узлов из которых состоят настоящие роботы: 
1. Робо-рука с двумя степенями свободы
2. Захват для робо-руки на основе серво-двигателя
3. Линейный актуатор, преобразующие вращение вала двигателя в прямолинейное движение.

### Scara Arm

[How to Build a 2 DOF Robotic Arm](
https://automaticaddison.com/how-to-build-a-2-dof-robotic-arm/)

[How To Perform a Pick and Place Task With a DIY SCARA Robot](
https://automaticaddison.com/how-to-perform-a-pick-and-place-task-with-a-diy-scara-robot/)

### Robot gripper
AR4 Robot Arm Servo Gripper  
[AR4 Robot Arm Servo Gripper video manual](https://www.youtube.com/watch?v=2JQeXzM5KEE)  
[AR4 Robot Arm Servo Gripper Models](https://www.anninrobotics.com/downloads)


### Linear actuators

[Homing with the AccelStepper library and a limit switch](
https://www.youtube.com/watch?v=0Xi7unlq1L4)

[3d printed gearbox powered linear servo actuator](
https://www.youtube.com/watch?v=-c1JRt7FlQs)

[3D Printed Linear Actuator](
https://www.youtube.com/watch?v=-C9e--3nvro)



