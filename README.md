# defining-class

class Car:
    def __init__(self,speed,para):
        self.speed = speed
        self.para = para
        print('Car with the maximum speed of', speed, para)
    
    def carFunc(self):
        print('Car with the maximum speed of', speed, para)
        

class Boat:
    def __init__(self,spee):
        self.spee = spee
        print('Boat with the maximum speed of', spee, 'knots')
    
    def boatFunc(self):
        print('Boat with the maximum speed of', spee, 'knots')
        
        

if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')
    q = int(input())
    queries = []
    for _ in range(q):
        args = input().split()
        vehicle_type, params = args[0], args[1:]
        if vehicle_type == "car":
            max_speed, speed_unit = int(params[0]), params[1]
            vehicle = Car(max_speed, speed_unit)
        elif vehicle_type == "boat":
            max_speed = int(params[0])
            vehicle = Boat(max_speed)
        else:
            raise ValueError("invalid vehicle type")
        fptr.write("%s\n" % vehicle)
    fptr.close()
