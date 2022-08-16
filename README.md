<h1>Team : KID MAI ORK</h1>
<hr>


The KID MAI ORK is a Self Driving bot which is programmed to drive autonomously and avoid obstacles with the use of sensors and motors present in the LEGO Spike prime.

TEAM DETAILS:

Team name : KID MAI ORK

Country : Thailand

Team members:  
  - Chanathip Pettewang.
  - Phongphat Wichaikul.
  - Wongsatorn Saehao.

Coach :
  - Wipada Sukkeaw.

ENGINEERING MATERIALS :

This repository contains engineering materials of the KID MAI ORK bot participating in the WRO Future Engineers competition in the season 2022.

CONTENTS :
-	t-photos: contains 2 photos of the team (an official one and one funny photo with all team members)
-	v-photos: contains 6 photos of the vehicle (from every side, from top and bottom) video contains the video.md file with the link to a video where driving demonstration exists
-	schemes: contains one or several schematic diagrams in form of JPEG, PNG or PDF of the electromechanical components illustrating all the elements (electronic components and motors) used in the vehicle and how they connect to each other.
-	src: contains code of control software for all components which were programmed to participate in the competition


Team photos:

-	Official photo


<img src="https://user-images.githubusercontent.com/83978237/184657760-e94129df-15c4-47ba-a867-9981c2ea7c54.jpg" width="500px">


-	Funny photo


<img src="https://user-images.githubusercontent.com/83978237/184657889-78e112aa-4fa6-4906-b55f-8c2d8a496930.jpg" width="500px">


Vehicle photos : Below are the photos of the 6 view of the self driving autonomous car.

-	FRONT VIEW

<img src="https://user-images.githubusercontent.com/83978237/184659027-5c73409c-ee2e-4c8d-bfbc-9f9b6cf85cba.jpg" width="500px">

-	BACK VIEW

<img src="https://user-images.githubusercontent.com/83978237/184659053-8057b6ff-f247-4d7e-a8fc-9fe45c23ec37.jpg" width="500px">

-	LEFT VIEW

<img src="https://user-images.githubusercontent.com/83978237/184659185-b75b7186-c593-447f-9d60-bb65c4f1ee33.jpg" width="500px">

-	RIGHT VIEW

<img src="https://user-images.githubusercontent.com/83978237/184659213-e39994c0-b65e-41f8-81a9-3ce40b6cedf1.jpg" width="500px">

-	TOP VIEW

<img src="https://user-images.githubusercontent.com/83978237/184659360-171108d5-b0a1-4759-bd2f-3715ddb97d44.jpg" width="500px">

-	BOTTOM VIEW

<img src="https://user-images.githubusercontent.com/83978237/184659377-f4530b94-93d8-4010-8381-15634222ca61.jpg" width="500px">


Link to YouTube video : https://youtu.be/k3jiCPzxsNE

***********************************

SCHEMATIC DIAGRAM :

Below is a schematic diagramatic representation consisting of all the electromechanical components (sensors, motors, bricks,) used in building the DEK IN NOMPHONG PROMOTE bot


<img src="" width="500px">


INTRODUCTION:

The KID MAI ORK bot is a Self Driving bot which is programmed to drive autonomously and avoid obstacles with the use of sensors and motors present in the LEGO Spike prime.

ELECTROMECHANICAL COMPONENTS : The KID MAI ORK bot is built using the Lego Spike prime. The brief description of each electromechanical component (sesors, motors and bricks) used in building this robot are given as folllows in order to understand the code and functionality of each component better.






Sensors:

-	ULTRASONIC SENSOR: The ultrasonic sensor is primarily used for the detection of obstacles and their avoidance. It is attached to the front of the robot.



<img src="https://raw.githubusercontent.com/sakol289/WRO2022_DEK-IN-NOMPHONG-PROMOTE/main/other/ULTRASONIC.jpg" width="500px">



-	COLOR SENSOR: The color sensors are used to detect change or for the comparison between two or more different color.



<img src="https://raw.githubusercontent.com/sakol289/WRO2022_DEK-IN-NOMPHONG-PROMOTE/main/other/COLOR.jpg" width="500px">



-	HUSKYLENS:The huskylens sensor are used to detect change or for the comparison between two or more different color. The huskylens were in the front of the bot.



<img src="https://raw.githubusercontent.com/sakol289/WRO2022_DEK-IN-NOMPHONG-PROMOTE/main/other/HUSKYLENS.jpg" width="500px">



Motors:

-	MEDIUM MOTOR: the medium motor is the primary driving base of our self driving robot.


<img src="https://raw.githubusercontent.com/sakol289/WRO2022_DEK-IN-NOMPHONG-PROMOTE/main/other/MEDIUMMOTOR.jpg" width="500px">


-	LARGE MOTOR: the large motor acts as a steering actuator in our robot.

<img src="https://raw.githubusercontent.com/sakol289/WRO2022_DEK-IN-NOMPHONG-PROMOTE/main/other/LARGEMOTOR.webp" width="500px">

Brick:
The spike prime Brick is the primary component of our robot. It supplies power to the robot and controls all its movements and actions. It is the part which stores all the programs neccessary for the functioning of the robot.

<img src="https://raw.githubusercontent.com/sakol289/WRO2022_DEK-IN-NOMPHONG-PROMOTE/main/other/spike.jpg" width="500px">

CODES:
-	WORD BLOCKS


<img src="" width="500px">



CODING:
The programming platform used for the coding of the self driving robot is Lego spike prime. Many programs were combined using My Block Builder. 
-	PYTHON
*******************************





    from projects.pyhuskylens import HuskyLens, ALGORITHM_OBJECT_CLASSIFICATION, clamp_int, ALGORITHM_COLOR_RECOGNITION
    from hub import button
    from spike import Motor

    motorfront = Motor('A')
    motor = Motor('B')

    setspeedfront = int(-30)
    setspeedturn = int(10)
    # motorfront.start()

    motor.start(setspeedfront)
    motorfront.run_to_position(0)

    hl = HuskyLens('F', debug=False)

    # เขียว = 1 เลี้ยวซ้าย
    # แดง = 2 เลี้ยวขวา

    # ล้อหน้า = A
    # ล้อหลัง = B

    # Get x/y loc of a face
    print("Starting face recognition")
    hl.set_alg(ALGORITHM_COLOR_RECOGNITION)




    while True:
        blocks = hl.get_blocks()
        print(blocks)
        if len(blocks) > 0:
            if blocks[0].ID == 1:
                pass
                # print(blocks)
                # motorfront.run_for_rotations(0.25,setspeedturn)
                if blocks[0].width >= 90:
                    # motor.stop()
                    motorfront.run_for_rotations(0.1)
                    motorfront.run_to_position(0)
                    motorfront.run_for_rotations(-0.1)
                    motorfront.run_to_position(0)
                    motor.stop()
                    # break

        


    # hl.set_alg(ALGORITHM_OBJECT_CLASSIFICATION)
    # motorfront.run_for_rotations(0.01, 100)
    # print(motorfront.get_degrees_counted())
    # while True:
    #     blocks = hl.get_blocks()
    #     print(blocks)
    #     if len(blocks) > 0:

    #         face_x = blocks[0].x
    #         error_x = (face_x-155)
        # print(error_x)
        # speed_x = 100 if error_x > 0 else -100
        # motorfront.run_for_rotations((error_x)//10,-100)
        # speed_x = -100 if error_x > 0 else 100
        # motorfront.run_for_degrees(clamp_int(error_x*0.2), speed_x)
        # motorfront.run_for_degrees(clamp_int(error_x*0.2), speed_x)

    # while not button.right.is_pressed():
    #     blocks = hl.get_blocks()
    #     print(blocks)
    #     if len(blocks) > 0:

    #         face_y = blocks[0].y
    #         error_y = (face_y-120)
    #         speed_y = 100 if error_y > 0 else -100
    #         motorfront.run_for_degrees(clamp_int(error_y*0.1), speed_y)

    #     if blocks[0].ID == 1:
    #     #    print("1")
    #        motorfront.run_for_rotations(0.25,setspeedturn)
    #    elif blocks[0].ID == 2:
    #     #    print("2")
    #        motorfront.run_for_rotations(-0.25,setspeedturn)
        # else:
        #    print("error")
    # else:
    #    print("error")
    # print(blocks)
