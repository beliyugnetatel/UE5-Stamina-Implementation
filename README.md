# UE5-Stamina-Implementation
Basic Stamina system implementaion using blueprints in Unreal Engine 5

Note: These methods may be suitable only for small indie projects and may not be appropriate for large-scale or professional projects.

# Basic Structure
This simple stamina logic was made by creating a Blueprint Class:

<img width="142" height="225" alt="image" src="https://github.com/user-attachments/assets/64003847-028e-4944-9f39-ee4189943d43" />

### After creating a Blueprint Class two main functions was made:
- [SpendingStamina function to control the spending stamina logic;](#spending-stamina)
- [GainingStamina function to control the gaining stamina logic.](#gaining-stamina)
- [PassiveRegStamina to implement the passive stamina regeneration logic.](#passive-regeneration)

<img width="315" height="112" alt="image" src="https://github.com/user-attachments/assets/ce179ef2-f262-4b9c-a467-5289611dcbf6" />

### Here are also some basic variables that we need:
- <b>Stamina (float)</b> to store the current amount of stamina;
- <b>MaxStamina (float)</b> to store the maximum amount of stamina (in my case max stamina = 100.0);
  
<img width="234" height="104" alt="image" src="https://github.com/user-attachments/assets/64a6b685-ccaf-4600-a29e-9485179e0cb5" />

# Spending Stamina 

<img width="1547" height="351" alt="image" src="https://github.com/user-attachments/assets/9237cc33-1916-4dc1-8e84-503c1ada6e5d" />

When called, this function changes the Stamina value depending on the provided Cost parameter. 
The subtraction of stamina is possible until the Stamina is greater than or equal to the Cost value, preventing negative stamina.

## Example of using

### Sprinting function

<img width="1071" height="476" alt="image" src="https://github.com/user-attachments/assets/ee5aeb9e-d6eb-4b69-a886-211f94549a73" />

When Shift is pressed, a timer is started using Set Timer by Event, causing the Spending Stamina function to be called every 0.1 seconds until Shift is released or there is enough stamina.

### How it looks on practice

![0108(2)](https://github.com/user-attachments/assets/0cd0f58e-18a1-4b4d-b38c-c1f7ebb19bca)

# Gaining Stamina

<img width="1294" height="319" alt="image" src="https://github.com/user-attachments/assets/d952fb58-cd1c-4f4f-ac6f-5b8aab2da356" />

When called, this function changes the Stamina value depending on the provided Cost parameter. 
The gaining of stamina is possible until the Stamina is less than or equal to the Max Stamina value.

## Example of using

### Passive Regeneration

Passive regeneration system is a great yet simple gameplay mechanic that allows player to come up with different playing styles.

### Here are some additional variables that we need:
- <b>CanRegen (Integer)</b> serving as a flag to detect if stamina can be regenerated right now (by default CanRegen = 0):
  - 0 - regeneration is possible;
  - greater than 0 - regeneration is not possible.
- (optional) <b>ActionTime (float)</b> gets "Get Game Time in Seconds" value while character is doing something that requires stamina. Used to make delay before passive regeneration starts for balance rreasons and to avoid bugs.

<img width="237" height="73" alt="image" src="https://github.com/user-attachments/assets/240b5f14-51fd-48a9-915f-26f2c5ff89da" />

### Passive Stamina Regeneration Function 

<img width="1545" height="536" alt="image" src="https://github.com/user-attachments/assets/edd9801e-51b6-4dd3-811e-7fdcdc12c65c" />

Using Set Timer by Event (BeginPlay) we can track if Stamina was reduced and if so to check if character is idle (not running, jumping or attacking, for example) to start passive regeneration. Before regeneration start there is 1 second delay to avoid unwanted problems/bugs and for balance reasons.

### How it looks on practice

### Active Regeneration
