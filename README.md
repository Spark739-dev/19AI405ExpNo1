<h1>ExpNo 1 :Developing AI Agent with PEAS Description</h1>
<h3>Name: VESHWANTH.</h3>
<h3>Register Number: 212224230300</h3>


<h3>AIM:</h3>
<br>
<p>To find the PEAS description for the given AI problem and develop an AI agent.</p>
<br>
<h3>Theory</h3>
<h3>Medicine prescribing agent:</h3>
<p>Such this agent prescribes medicine for fever (greater than 98.5 degrees) which we consider here as unhealthy, by the user temperature input, and another environment is rooms in the hospital (two rooms). This agent has to consider two factors one is room location and an unhealthy patient in a random room, the agent has to move from one room to another to check and treat the unhealthy person. The performance of the agent is calculated by incrementing performance and each time after treating in one room again it has to check another room so that the movement causes the agent to reduce its performance. Hence, agents prescribe medicine to unhealthy.</p>
<hr>
<h3>PEAS DESCRIPTION:</h3>
<table>
  <tr>
    <td><strong>Agent Type</strong></td>
    <td><strong>Performance</strong></td>
     <td><strong>Environment</strong></td>
    <td><strong>Actuators</strong></td>
    <td><strong>Sensors</strong></td>
  </tr>
    <tr>
    <td><strong>Medicine prescribing agent</strong></td>
    <td><strong>Treating unhealthy, agent movement</strong></td>
     <td><strong>Rooms, Patient</strong></td>
    <td><strong>Medicine, Treatment</strong></td>
    <td><strong>Location, Temperature of patient</strong></td>
  </tr>
</table>
<hr>
<H3>DESIGN STEPS</H3>
<h3>STEP 1:Identifying the input:</h3>
<p>Temperature from patients, Location.</p>
<h3>STEP 2:Identifying the output:</h3>
<p>Prescribe medicine if the patient in a random has a fever.</p>
<h3>STEP 3:Developing the PEAS description:</h3>
<p>PEAS description is developed by the performance, environment, actuators, and sensors in an agent.</p>
<h3>STEP 4:Implementing the AI agent:</h3>
<p>Treat unhealthy patients in each room. And check for the unhealthy patients in random room</p>
<h3>STEP 5:</h3>
<p>Measure the performance parameters: For each treatment performance incremented, for each movement performance decremented</p>

<H3>PROGRAM:</H3>

    class MedicineAgent:
        def __init__(self, room_temps):
            self.room_temps = room_temps
            self.current_room = "A"
            self.performance = 0
            self.visited = set()
    
        def sense_temperature(self):
            return self.room_temps[self.current_room]
    
        def treat_patient(self):
            print(f"Treating patient in Room {self.current_room}")
            self.performance += 10
    
        def move(self):
            print(f"Moving from Room {self.current_room}")
            self.performance -= 1
            self.current_room = "B" if self.current_room == "A" else "A"
    
        def run(self):
            for _ in range(2):  # Two rooms
                print(f"\nChecking Room {self.current_room}")
                self.visited.add(self.current_room)
                temp = self.sense_temperature()
                print(f"Temperature: {temp}°F")
    
                if temp > 98.5:
                    self.treat_patient()
                else:
                    print("Patient is healthy.")
    
                if len(self.visited) < 2:
                    self.move()
    
            print("\nFinal Performance Score:", self.performance)
    
    
    
    room_A_temp = float(input("Enter temperature for Room A: "))
    room_B_temp = float(input("Enter temperature for Room B: "))
    
    rooms = {"A": room_A_temp, "B": room_B_temp}
    
    agent = MedicineAgent(rooms)
    agent.run()

<H3>OUTPUT:</H3>

<img width="1398" height="309" alt="image" src="https://github.com/user-attachments/assets/076457ff-c5ea-4a76-b7eb-7e38af9203f5" />
