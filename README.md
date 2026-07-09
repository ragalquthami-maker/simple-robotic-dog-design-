# simple-robotic-dog-design-
Preliminary mechanical design for a simple quadruped robot
# Simple Robotic Dog — Preliminary Mechanical Design

This is my initial mechanical design for a simple quadruped robot, done as coursework. The main goal was to understand the basic mechanics that let a robot stand and walk.

## The body

The chassis is a flat rectangular base: 200mm long, 100mm wide, 15mm thick. I plan to 3D print it in PLA or cut it from thin acrylic. Total weight of the robot should stay around 800g to 1.2kg based on the motors I selected.

![Overview](images/overview.jpeg)

## The legs

Each leg has two parts connected at a knee: the femur (upper part, connects to the body at the hip) and the tibia (lower part, ends in the foot). I used a bent Z shape for the leg to simplify the joint control. There are four legs total, placed symmetrically at the corners of the body.

![Leg close-up](images/leg-closeup.jpeg)

## Joints and degrees of freedom

Each leg has 2 joints: the hip and the knee. That gives 2 degrees of freedom per leg, and 8 total for the whole robot. A third joint per leg would allow side-to-side movement, but I kept the design at 8 DOF for simplicity.

## Picking the motors

I compared three servo options. The SG90 (about 1.8 kg·cm torque) does not provide enough torque for this load. The DS3218 (about 20 kg·cm) provides more torque than needed unless the robot exceeds 1.5kg. I selected the MG996R, rated at 10–13 kg·cm, which matches the calculated torque requirement with a safety margin.

## Torque calculation

I calculated the required torque for the knee joint. During walking, when the robot balances on two legs, each leg carries about half the total weight. For a 1kg robot, that is 0.5kg (4.9N) per leg.

Using the tibia length as the moment arm (0.08m):

τ = F × d = 4.9N × 0.08m ≈ 0.392 N·m ≈ 4 kg·cm (theoretical value)

This value does not include dynamic loads from movement or leg angle. Adding a safety factor of 2–3x gives a required torque of 8–12 kg·cm, which matches the MG996R's rated torque.

## Staying balanced

The robot's center of gravity must stay within the support polygon formed by the legs touching the ground. The battery, the heaviest component, is placed at the center of the body to keep the weight balanced.

![Top view](images/top-view.jpeg)

## How it walks

I used a wave gait for this design. Only one leg lifts at a time, while the other three legs stay on the ground for stability. The lift order is: back-right, front-right, back-left, front-left. A trot gait (lifting two diagonal legs together) would increase speed, but requires more precise timing and reduces stability.

## Expected mechanical problems

Several mechanical issues are likely during construction. Joint friction from plastic-on-plastic contact can be reduced with small bushings. Gear backlash can be reduced using metal-gear servos. Uneven weight distribution can occur if the battery or wiring is not centered. Wire strain can occur during leg movement, so extra slack is needed. Foot slipping can occur on smooth surfaces, so rubber pads are added to the feet. Servo stalling can occur if the load exceeds the calculated torque, which is why the safety factor is included.

---

This is a preliminary design. It covers body dimensions, joint count, torque calculation, balance, and gait as the core mechanical elements of the robot.
