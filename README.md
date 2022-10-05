# Cab-service
This is a python program for a cab service.
This Cab service has 5 types of vehicles. 
-Cars 
-Vans 
-3 Wheelers 
-Lorries 
-Trucks

***Details of each vehicle as follows***

-Car:
maximum number of passengers - 3 and 4
AC/ Non AC

-Van:
Maximum number of passengers - 6 and 8
AC/ Non AC

-3 Wheelers:
Maximum number of passengers - 3

-Trucks:
Size – 7 ft and 12 ft

-Lorry:
Max load and size - 2500kg and 3500kg

Customer can be able to choose a vehicle according to his/ her requirements. Vehicles should 
be in a queue and the next available vehicle must be given, which matches the customer 
requirements.
Following features have to be in the program,
• Add a new vehicle to the system
• Remove a vehicle from the system
• Assign a job (hire)
• Release form assigned job (hire) after completing
• See available vehicles in each category.

+++++++++++++++++++++++++++++ CODE ++++++++++++++++++++++++++++++++++++
carList = []
vanList = []
wheelerList = []
truckList = []
lorryList = []
deleteCars = []
deleteVans = []
deleteWheel = []
deleteTruck = []
deleteLorry = []


class Car():

    def __init__(self ,  model , passengers , year , color , mode):

        self.passengers = passengers
        self.model = model
        self.year = year
        self.color = color
        self.mode = mode


    def  vehicleDetail(self):
        return " 1.MODEL : %s\n 2.PASSENGER : %s\n 3.YEAR : %s\n 4.COLOR :%s\n 5.AC/non-AC : %s\n" % (self.model, self.passengers,self.year,  self.color, self.mode)


class Van():

    def __init__(self ,  passengers , model , year , color , mode):

        self.passengers = passengers
        self.model = model
        self.year = year
        self.color = color
        self.mode = mode

    def  vehicleDetail(self):
        return " 1.MODEL : %s\n 2.PASSENGER : %s\n 3.YEAR : %s\n 4.COLOR :%s\n 5.AC/non-AC : %s\n" % (self.model, self.passengers,self.year,  self.color, self.mode)


class ThreeWheeler():

    def __init__(self , passengers , model , year , color):
        self.passengers = passengers
        self.model = model
        self.year = year
        self.color = color

    def  vehicleDetail(self):
        return " 1.MODEL : %s\n 2.PASSENGER : %s\n 3.YEAR : %s\n 4.COLOR :%s\n" % (self.model, self.passengers,self.year,  self.color)

class Trucks():

    def __init__(self ,  model , size):
        self.size = size
        self.model = model

    def  vehicleDetail(self):
        return " 1.MODEL : %s\n 2.SIZE : %s\n" % (self.model, self.size)

class Lorry():

    def __init__(self ,  load  , model):
        self.model = model
        self.load = load

    def  vehicleDetail(self):
        return " 1.MODEL : %s\n 2.LOAD : %s\n" % (self.model, self.load)


while (True):

    print("\nWELCOME TO CAB SERVICE")
    print("\n1.Add New Vehicle\n2.Remove Vehicle\n3.Hire Vehicle\n4.Release Hired Vehicle\n5.See Available Vehicle\n6.Exit")

    choice1 = int(input("Enter your choice (1/2/3/4/5/6) : "))

    # ADD NEW VEHICLE
    if (choice1 == 1):
        print("\t\t1.Car\n\t\t2.Van\n\t\t3.Three Wheel\n\t\t4.Truck\n\t\t5.Lorry\n")
        choice2 = int(input("Enter your choice (1/2/3/4/5) : "))

        # adding cars to the system
        if (choice2 == 1):
            model = input("Enter vehicle model : ")
            passengers = input("Enter number of passengers : ")
            year = input("Enter manufactured year : ")
            color = input("Enter vehicle color : ")
            mode = input("Enter AC or non-AC : ")
            print("\n")


            car1 = Car(model, passengers, year, color, mode)
            carList.append(car1)
            for i in range(0, len(carList)):
                print("\nCar %d\n" % (i + 1))
                print(carList[i].vehicleDetail())
            print("\nVehicle Added Successfully!!")


        # adding vans to the system
        if (choice2 == 2):
            model = input("Enter vehicle model : ")
            passengers = input("Enter number of passengers : ")
            year = input("Enter manufactured year : ")
            color = input("Enter vehicle color : ")
            mode = input("Enter AC or non-AC : ")
            print("\n")

            van1 = Van(model, passengers, year, color, mode)
            vanList.append(van1)
            for i in range(0, len(vanList)):
                print("\nVan %d\n" % (i + 1))
                print(vanList[i].vehicleDetail())
            print("\nVehicle Added Successfully!!")

        # adding threewheelers to the system
        if (choice2 == 3):
            model = input("Enter vehicle model : ")
            passengers = input("Enter number of passengers : ")
            year = input("Enter manufactured year : ")
            color = input("Enter vehicle color : ")
            print("\n")

            wheeler1 = ThreeWheeler(model, passengers, year, color)
            wheelerList.append(wheeler1)
            for i in range(0, len(wheelerList)):
                print("\nWheeler %d\n" % (i + 1))
                print(wheelerList[i].vehicleDetail())
            print("\nVehicle Added Successfully!!")

        # adding trucks to the system
        if (choice2 == 4):
            model = input("Enter vehicle model : ")
            size = input("Enter the size : ")
            print("\n")

            truck1 = Trucks(model, size)
            truckList.append(truck1)
            for i in range(0, len(truckList)):
                print("\ntruck %d\n" % (i + 1))
                print(truckList[i].vehicleDetail())
            print("\nVehicle Added Successfully!!")

        # adding lorries to the system
        if (choice2 == 5):
            model = input("Enter vehicle model : ")
            load = input("Enter the load : ")
            print("\n")

            lorry1 = Lorry(model, load)
            lorryList.append(lorry1)
            for i in range(0, len(lorryList)):
                print("\nlorry %d\n" % (i + 1))
                print(lorryList[i].vehicleDetail())
            print("\nVehicle Added Successfully!!")

    # REMOVE VEHICLE
    elif (choice1 == 2):

        print("\n\t\tREMOVE VEHICLE FROM THE SYSTEM")

        print("\t\t1.Car\n\t\t2.Van\n\t\t3.Three Wheel\n\t\t4.Truck\n\t\t5.Lorry\n")
        choice2 = int(input("Enter your choice (1/2/3/4/5) : "))

        # car
        if(choice2 == 1):

            if len(carList) < 1:
                print('\nSorry there are no vehicles currently in Cab Service\n')
                print("Add vehicle first\n")
                continue

            for i in range(0, len(carList)):
                print("\nCar %d\n" % (i + 1))
                print(carList[i].vehicleDetail())

            remove = int(input("Enter the number of the car which you want to remove : "))
            carList.pop(remove - 1)
            print("Vehicle deleted Successfully!!")

        # van
        elif(choice2 == 2):

            if len(vanList) < 1:
                print('\nSorry there are no vehicles currently in Cab Service\n')
                print("Add vehicle first\n")
                continue

            for i in range(0, len(vanList)):
                print("\nVan %d\n" % (i + 1))
                print(vanList[i].vehicleDetail())

            remove = int(input("Enter the number of the van which you want to remove : "))
            vanList.pop(remove - 1)
            print("Vehicle deleted Successfully!!")

        # Wheeler
        elif (choice2 == 3):

            if len(wheelerList) < 1:
                print('\nSorry there are no vehicles currently in Cab Service\n')
                print("Add vehicle first\n")
                continue

            for i in range(0, len(wheelerList)):
                print("\nWheeler %d\n" % (i + 1))
                print(wheelerList[i].vehicleDetail())

            remove = int(input("Enter the number of the three wheeler which you want to remove : "))
            wheelerList.pop(remove - 1)
            print("Vehicle deleted Successfully!!")

        # truck
        elif (choice2 == 4):

            if len(truckList) < 1:
                print('\nSorry there are no vehicles currently in Cab Service\n')
                print("Add vehicle first\n")
                continue

            for i in range(0, len(truckList)):
                print("\ntruck %d\n" % (i + 1))
                print(truckList[i].vehicleDetail())

            remove = int(input("Enter the number of the truck which you want to remove : "))
            truckList.pop(remove - 1)
            print("Vehicle deleted Successfully!!")

        # lorry
        elif (choice2 == 5):

            if len(lorryList) < 1:
                print('\nSorry there are no vehicles currently in Cab Service\n')
                print("Add vehicle first\n")
                continue

            for i in range(0, len(lorryList)):
                print("\nlorry %d\n" % (i + 1))
                print(lorryList[i].vehicleDetail())

            remove = int(input("Enter the number of the lorry which you want to remove : "))
            lorryList.pop(remove - 1)
            print("Vehicle deleted Successfully!!")

    # HIRE VEHICLE
    elif (choice1 == 3):

        print("\n\t\tHIRE VEHICLE\t\t")
        print("\t\t1.Car\n\t\t2.Van\n\t\t3.Three Wheel\n\t\t4.Truck\n\t\t5.Lorry\n")
        choice3 = int(input("Enter your choice (1/2/3/4/5) : "))

        # car
        if (choice3 == 1):
            print("\n\t\tHIRE CAR \n")
            passengerNum = int(input("Enter number of passengers : "))
            if (passengerNum > 4):
                print("Maximum number of passengers is 4. Enter valid number.")
                continue
            ac = input("Enter AC or non-AC : ")
            if(len(carList) != 0):
                print("Hired the required Vehicle successfully!!")

            try:
                deleteCars.append(carList.pop(0))

            except:
                print("\nSorry. Vehicles are not available at the moment.")

        # van
        if (choice3 == 2):
            print("\n\t\tHIRE VAN \n")
            passengerNum = int(input("Enter number of passengers : "))
            if (passengerNum > 8):
                print("Maximum number of passengers is 8. Enter valid number.")
                continue
            ac = input("Enter AC or non-AC : ")
            if (len(vanList) != 0):
                print("Hired the required Vehicle successfully!!")

            try:
                deleteVans.append(vanList.pop(0))

            except:
                print("\nSorry. Vehicles are not available at the moment.")

        # Wheeler
        if (choice3 == 3):
            print("\n\t\tHIRE THREE WHEELER \n")
            passengerNum = int(input("Enter number of passengers : "))
            if (passengerNum > 3):
                print("Maximum number of passengers is 3. Enter valid number.")
                continue
            if (len(wheelerList) != 0):
                print("Hired the required Vehicle successfully!!")

            try:
                deleteWheel.append(wheelerList.pop(0))

            except:
                print("\nSorry. Vehicles are not available at the moment.")

        # truck
        if (choice3 == 4):
            print("\n\t\tHIRE TRUCK \n")
            size = int(input("Enter the size of the truck : "))
            if ( 7 >= size >= 12 ):
                print("Truck size is not valid")
                continue
            if (len(truckList) != 0):
                print("Hired the required Vehicle successfully!!")

            try:
                deleteTruck.append(truckList.pop(0))

            except:
                print("\nSorry. Vehicles are not available at the moment.")

        # lorry
        if (choice3 == 5):
            print("\n\t\tHIRE LORRY \n")
            loads = int(input("Enter the load of the lorry : "))
            if (2500 >= loads and loads >= 3500):
                print("Lorry load is not valid")
                continue
            if (len(lorryList) != 0):
                print("Hired the required Vehicle successfully!!")

            try:
                deleteLorry.append(lorryList.pop(0))

            except:
                print("\nSorry. Vehicles are not available at the moment.")

    # RELEASE HIRED VEHICLE
    elif (choice1 == 4):

        print("\n\t\tRELEASE HIRED VEHICLE ")

        print("\t\t1.Car\n\t\t2.Van\n\t\t3.Three Wheel\n\t\t4.Truck\n\t\t5.Lorry\n")
        choice2 = int(input("Enter your choice (1/2/3/4/5) : "))

        # car
        if (choice2 == 1):

            if len(deleteCars) > 0:
                for i in range(0, len(deleteCars)):
                    print("\nCar %d\n" % (i + 1), deleteCars[i].vehicleDetail())

                    select = int(input("\nEnter the car number which you want to end hire : "))
                    carList.append(deleteCars.pop(select - 1))

                print("\nReleased the selected hired car successfully!! ")

            else:
                print('\nSorry there are no vehicles currently in Cab Service')
                print("Add vehicle first\n")

        # van
        if (choice2 == 2):

            if len(deleteVans) > 0:
                for i in range(0, len(deleteVans)):
                    print("\nVan %d\n" % (i + 1), deleteVans[i].vehicleDetail())

                    select = int(input("\nEnter the van number which you want to end hire : "))
                    vanList.append(deleteVans.pop(select - 1))

                print("\nReleased the selected hired van successfully!! ")

            else:
                print('\nSorry there are no vehicles currently in Cab Service')
                print("Add vehicle first\n")

        # Wheelers
        if (choice2 == 3):

            if len(deleteWheel) > 0:
                for i in range(0, len(deleteWheel)):
                    print("\nThree Wheeler %d\n" % (i + 1), deleteWheel[i].vehicleDetail())

                    select = int(input("\nEnter the three wheeler number which you want to end hire : "))
                    wheelerList.append(deleteWheel.pop(select - 1))

                print("\nReleased the selected hired three wheeler successfully!! ")

            else:
                print('\nSorry there are no vehicles currently in Cab Service')
                print("Add vehicle first\n")

        # truck
        if (choice2 == 4):

            if len(deleteTruck) > 0:
                for i in range(0, len(deleteTruck)):
                    print("\ntruck %d\n" % (i + 1), deleteTruck[i].vehicleDetail())

                    select = int(input("\nEnter the truck number which you want to end hire : "))
                    truckList.append(deleteTruck.pop(select - 1))

                print("\nReleased the selected hired truck successfully!! ")

            else:
                print('\nSorry there are no vehicles currently in Cab Service')
                print("Add vehicle first\n")

        # lorry
        if (choice2 == 5):

            if len(deleteLorry) > 0:
                for i in range(0, len(deleteLorry)):
                    print("\nlorry %d\n" % (i + 1), deleteLorry[i].vehicleDetail())

                    select = int(input("\nEnter the lorry number which you want to end hire : "))
                    lorryList.append(deleteLorry.pop(select - 1))

                print("\nReleased the selected hired lorry successfully!! ")

            else:
                print('\nSorry there are no vehicles currently in Cab Service')
                print("Add vehicle first\n")

    # SEE AVAILABLE VEHICLE

    elif (choice1 == 5):

        print("\n\t\tAVAILABLE VEHICLES")

        print("\t\t1.Car\n\t\t2.Van\n\t\t3.Three Wheel\n\t\t4.Truck\n\t\t5.Lorry\n")
        choice2 = int(input("Enter your choice (1/2/3/4/5) : "))

        # car
        if (choice2 == 1):

            if len(carList) < 1:
                print('\nSorry there are no vehicles currently in Cab Service\n')
                continue

            for i in range(0, len(carList)):
                print("\nCar %d\n" % (i + 1), carList[i].vehicleDetail())

        # van
        if (choice2 == 2):

            if len(vanList) < 1:
                print('\nSorry there are no vehicles currently in Cab Service\n')
                continue

            for i in range(0, len(vanList)):
                print("\nVan %d\n" % (i + 1), vanList[i].vehicleDetail())

        # wheeler
        if (choice2 == 3):

            if len(wheelerList) < 1:
                print('\nSorry there are no vehicles currently in Cab Service\n')
                continue

            for i in range(0, len(wheelerList)):
                print("\ntruck %d\n" % (i + 1), wheelerList[i].vehicleDetail())

        # truck
        if (choice2 == 4):

            if len(truckList) < 1:
                print('\nSorry there are no vehicles currently in Cab Service\n')
                continue

            for i in range(0, len(truckList)):
                print("\nWheeler %d\n" % (i + 1), truckList[i].vehicleDetail())

        # lorry
        if (choice2 == 5):

            if len(lorryList) < 1:
                print('\nSorry there are no vehicles currently in Cab Service\n')
                continue

            for i in range(0, len(lorryList)):
                print("\nlorry %d\n" % (i + 1), lorryList[i].vehicleDetail())

    # EXIT SYSTEM
    elif (choice1 == 6):
        print('\t\t\nTHANK YOU!!')
        break
