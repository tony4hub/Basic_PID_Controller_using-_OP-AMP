# Basic_PID_Controller_using-_OP-AMP
Aim:
To achieve stable voltage control across a system using a PID controller designed with operational amplifiers (OPAMPs).

Abstract:
A PID controller is widely used in industrial process control for regulating variables such as temperature, flow, pressure, speed, and many other parameters. Nearly 95% of closed-loop operations in industrial automation rely on PID controllers. PID stands for Proportional-Integral-Derivative, and these three modes collectively generate a control signal using a feedback mechanism to maintain the desired process variable with high accuracy and stability.

PID control is a well-established method for driving a system toward a target value. It is commonly applied in temperature control, chemical processes, scientific experiments, and automation systems. By continuously comparing the actual output with the reference setpoint, the PID controller minimises error and ensures the system output remains as close as possible to the desired level.

In this project, analogue electronic components, primarily OPAMPs, are used to design and implement a PID controller. As the name indicates, the controller operates based on three parameters: proportional, integral, and derivative. Each control block is first designed and tested individually, then integrated to form the complete PID controller. The system under consideration is a voltage-controlled plant, and the controller is made tunable. The LM741 OPAMP is used for the implementation, along with suitably selected resistors, capacitors, and potentiometers, as shown in the circuit diagram.

In many real-world applications, voltage-sensitive systems require steady and precise tuning relative to a reference voltage. A PID controller becomes essential in achieving this controlled response.

In this project, the reference voltage serves as the input. The controller calculates the error, processes it, and drives the system accordingly while continuously receiving feedback to adjust the response. In our implementation, the controlled system is an LED. The following sections illustrate the design of the PID controller using OPAMPs.

Block diagram:
<img width="4462" height="1813" alt="PID Diagram-01" src="https://github.com/user-attachments/assets/6926aeb1-926b-4991-95c6-eda49dd1005a" />

The error counted over the measured value and the reference will be given as input to the PID controller.
PID controller outputs a voltage value that will be one step closer to attaining the reference voltage.
Our system, in this case, is LED. The voltmeter acts as a reading component that sends feedback through the Buffer back to the PID controller.

Circuit diagram:
<img width="1289" height="781" alt="Screenshot 2025-11-18 213249" src="https://github.com/user-attachments/assets/daa9d59e-64a2-4b91-afba-fb17f0e0aa42" />

Traverse Through Circuit

An operational amplifier (op-amp) is a fundamental building block in analog electronics. By adding a few external components, it can be configured to perform a wide range of mathematical operations.

1) Inverting Op-Amp

The inverting amplifier configuration reverses the polarity of the input voltage. In this setup, the output voltage 

	​

 is fed back to the inverting input terminal through the feedback resistor 
𝑅
𝑓
R
f
	​

. This feedback arrangement controls the gain and stability of the amplifier.

2) Differentiator

When the input resistor 
𝑅
1
R
1
	​

 in an inverting amplifier is replaced by a capacitor, the circuit functions as a differentiator.

As the name implies, this circuit performs the mathematical operation of differentiation, meaning the output waveform represents the derivative of the input signal.
The general expression for the differentiator is:

𝑉
𝑜
=
−
𝑅
𝐶
𝑑
𝑉
𝑖
𝑛
𝑑
𝑡
V
o
	​

=−RC
dt
dV
in
	​

	​


The negative sign indicates a 180-degree phase shift between the input and the output.

3) Integrator

If the feedback resistor 
𝑅
𝑓
R
f
	​

 in an inverting amplifier is replaced with a capacitor, the circuit becomes an integrator.

The integrator performs the mathematical operation of integration, meaning the output waveform represents the time integral of the input signal. The equation is:

𝑉
𝑜
=
−
1
𝑅
𝐶
∫
𝑉
𝑖
𝑛
 
𝑑
𝑡
V
o
	​

=−
RC
1
	​

∫V
in
	​

dt

The output is proportional to the accumulated (integrated) value of the input signal over time, where 
𝑅
𝐶
RC defines the time constant of the circuit.

4) Difference Amplifier

A difference amplifier produces an output equal to the difference between the signals applied at its two input terminals.

This configuration can be analyzed using the principle of superposition by considering each input source independently. The circuit is widely used in applications requiring precise differential signal measurement.

5) Buffer or Voltage Follower

A voltage buffer, also known as a voltage follower or unity-gain amplifier, provides a gain of 1. It is a special case of the non-inverting amplifier with maximum negative feedback.

Although it does not amplify voltage, the buffer plays an essential role in preventing loading effects. It isolates the input stage from the output stage by presenting high input impedance and low output impedance, ensuring minimal signal loss.

By understanding these basic op-amp configurations and their functions, we can now move forward and analyze the earlier-designed circuit used to implement the PID controller.


