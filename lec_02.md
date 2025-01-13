# Lecture 2

## Risks and Benefits of AI

* Benefits:
  * Decrease repetitive work
  * Increase production of goods and services
  * Accelerate scientific research
 
* Risks:
  * Lethal autonomous weapons
  * Surveillance and persuasion
  * Based decision making
  * Impact on employment
  * Safety-critical applications
  * Cybersecurity threats
 
## Agents and Environemnts

* **Agent** - Anything that is percieving its enviroment through **sensors** and acting on its environemnt through **actuators**

![image](https://github.com/user-attachments/assets/778f503c-3e4e-423c-b47c-069a89baedbf)

* The **agent function** maps from percet histories to actions:

![image](https://github.com/user-attachments/assets/0bb12174-3688-472f-b0bc-f9c2c36065e6)

* The agent program runs on the physical architecture to produce _f_

## Rationality

* A **Rational Agent** chooses whichever action maximizes the expected value pf the performance measure given the percept sequence to date

* Rational =/= omniscient
  * Percepts may not supply all relevant information
* Rational =/= clairvoyant
  * Action outcomes may not be as expected
* Hence, rational =/= successful

* **Rational => exploration, learning, autonomy**

## PEAS

* To design a rational agent, we must spexify the task environment. Consider the task of designing an automated taxi:

* **Performance Measure** - Safety, destination, profits, legality, comfort...
* **Environment** - US streets/freeways, traffic, pedestrians, weather...
* **Actuators** - Steering, accelerator, brake, horn, speaker/display...
* **Sensors** - Video, accelerometers, gauges, engine sensors, keyboard, GPS...

## Environemnt Types

* **Fully ot partially observable:** At each time step, can the agent's sensors detect all relevant information
* **Single or multi-agent:** does one or more entities have the ability to sense and respond to it's environment
* **Deterministic or nondeterministic:** Is the next state completely determined by the current one or random
* **Episodic or Sequential:** Does the current decision affect future decisions or does the agent act episodically
* **Static or Dynamic:** Can the environment change while the agent is moving and making its decisions

![image](https://github.com/user-attachments/assets/4eabc1d5-b8a4-453d-90c3-6de6ec2cf3c1)

## Agent Types

* Four basic types in order of increasing generallity
  * Simple reflex agents
  * Reflex agents with state
  * Goal-based agents
  * Utility-based agents

* Simple Reflex agents
![image](https://github.com/user-attachments/assets/7afe1a93-3e83-469b-ae4f-916491238a95)

* Reflex agents with state
![image](https://github.com/user-attachments/assets/6a4b7385-0336-4f7f-9879-c194920253ba)

* Goal-based agents
![image](https://github.com/user-attachments/assets/0f98aaa9-2671-4c94-9b3c-188329a8f5f8)

* Utility-based agents
![image](https://github.com/user-attachments/assets/26b943fc-c670-48e1-ba7d-e151e60be5cf)

* Learning agents
![image](https://github.com/user-attachments/assets/c6dbe6a3-d57f-410a-bac9-54abd62f2cda)

