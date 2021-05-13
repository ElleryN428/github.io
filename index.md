test_UltrasonicSensor = UltrasonicSensor(Port.S4)
test_motorA = Motor(Port.A)
test_motorB = Motor(Port.B)

while True:
    print(test_UltrasonicSensor.distance())
    if test_UltrasonicSensor.distance() < 100:
        test_motorA.brake()
        test_motorB.brake()
        test_motorB.run_time(250, 2200, then=Stop.HOLD, wait=False)
        test_motorA.run_time(-250,2200, then=Stop.HOLD, wait=True)
    
    else:
        test_motorA.run(500)
        test_motorB.run(500)    
