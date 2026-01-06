# UE5-Stamina-Implementation
Basic Stamina system implementaion using blueprints in Unreal Engine 5

## Basic Structure
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
  
<img width="315" height="137" alt="image" src="https://github.com/user-attachments/assets/27269875-114a-495d-a956-874dc314ee1f" />

## Spending Stamina 

<img width="1547" height="351" alt="image" src="https://github.com/user-attachments/assets/9237cc33-1916-4dc1-8e84-503c1ada6e5d" />

When called, this function changes the Stamina value depending on the provided Cost parameter. 
The gaining of stamina is possible until the Stamina is less than or equal to the Max Stamina value.

### Examples of using

## Gaining Stamina

<img width="1294" height="319" alt="image" src="https://github.com/user-attachments/assets/d952fb58-cd1c-4f4f-ac6f-5b8aab2da356" />

When called, this function changes the Stamina value depending on the provided Cost parameter. 
The subtraction of stamina is possible until the Stamina is greater than or equal to the Cost value, preventing negative stamina.

### Examples of using

## Passive Regeneration


