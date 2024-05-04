# What is Magical Arena ?

Magical Arena is an engaging turn-based battle game where players face off against each other until one emerges victorious by depleting their opponent's health points. Players are defined by their health, strength, and attack attributes, all of which are positive integers. The game employs dice rolls to determine the outcome of attacks and defenses, adding an element of chance and strategy to each encounter.

## Problem Statement

Design a Magical Arena. Every Player is defined by a “health” attribute, “strength” attribute and an “attack” attribute - all positive integers. The player dies if his health attribute touches 0. 

Any two player can fight a match in the arena. Players attack in turns. Attacking player rolls the attacking dice and the defending player rolls the defending dice. The “attack”  value multiplied by the outcome of the attacking dice roll is the damage created by the attacker. The defender “strength” value, multiplied by the outcome of the defending dice is the damage defended by the defender. Whatever damage created by attacker which is in excess of the damage defended by the defender will reduce the “health” of the defender. Game ends when any players health reaches 0

Player with lower health attacks first at the start of a match. 

Assume two players . Player A 50 health 5 strength 10 attack Player B 100 health 10 stregnth and 5 attack . Attacking die and Defending die are both 6 sided die with values ranging from 1- 6

Player A attacks and rolls die. Die roll : 5 . Player B defends and rolls die. Die roll 2

Attack damage is 5 * 10 = 50 ; Defending strength = 10 * 2 = 20 ; Player B health reduced by 30 to 70

Player B attacks and rolls die. Die roll : 4. Player A defends and rolls die. Die Roll 3

Attack damage is 4 * 5 = 20 ; Defending strength = 5 * 3 = 15 ; Player A health reduced by 5 to 45

And so on

## Rules of the Game:
You can use Java, Go or Node.js to implement the solution, without using any third-party libraries or frameworks ( common and essential helper libs and packages are allowed ex. math.rand() is ok.

The player with lower health attacks first at the beginning of a match.

## Solution & Approach

This is a simple Java implementation of the Magical Arena game. The Magical Arena is a turn-based battle game where two players engage in combat until one of them loses all their health points.

1. **Observer Pattern (Audience)**:
   - `Audience` observes the battle events.
   - Updates are received and relevant information is printed.

2. **State Management (BattleContext)**:
   - Manages the battle state using the State pattern.
   - Ensures the battle starts only when in progress.

3. **Battle Execution (BattleMain)**:
   - Orchestrates the battle between two `TeamMember` instances.
   - Simulates battle rounds until one loses all health.

4. **Observer Interface (GameObserver)**:
   - Defines update method for observers.
   - Implemented by concrete observers like `Audience`.

5. **Game Status (GameStatus)**:
   - Enum defining battle states like `IN_PROGRESS` and `FINISHED`.

6. **Main Class**:
   - Initializes game components and triggers battle.

7. **TeamMember Interface and Implementation**:
   - Defines common behavior and specifics for battle participants.


## Class Diagram

![chatuml-diagram](https://github.com/bhartik021/swiggy-assignment/assets/75694208/f378c177-15ca-497a-b548-0c9af182bb81)

## Features

- **Player Attributes**: Players have attributes such as health, strength, and attack, which determine their effectiveness in combat.
- **Turn-Based Combat**: Engage in thrilling turn-based battles where strategy and luck play crucial roles in determining the outcome.
- **Dice Rolls**: Attacks and defenses are resolved using dice rolls, adding an element of unpredictability to each encounter.
- **Dynamic Damage Calculation**: Damage inflicted and defended is calculated dynamically based on player attributes and dice rolls.
- **Game End Conditions**: The game ends when one player's health reaches 0, declaring the other player as the winner.

### Project Structure

- `src/main/java` (Main.java): Contains the main source code files.
- `src/test/java` (PlayerTest.java and MagicalArenaTest.java): Contains the test source code files.
- `pom.xml`: Maven project configuration file.
  
```bash
swiggyAssignment
├── out
│   └── production
│       └── swiggyAssignment
│           ├── Audience.class
│           ├── BattleContext.class
│           ├── BattleMain.class
│           ├── GameObserver.class
│           ├── GameStatus.class
│           ├── Main.class
│           ├── TeamMember.class
│           └── Wizard.class
├── src
│   ├── Audience.java
│   ├── BattleContext.java
│   ├── BattleMain.java
│   ├── GameObserver.java
│   ├── GameStatus.java
│   ├── Main.java
│   ├── TeamMember.java
│   └── Wizard.java
└── swiggyAssignment.iml
```

### How to Build and Run

To build and run the Magical Arena project locally, follow these steps:

#### Prerequisites

- **Java Development Kit (JDK)**: Essential for compiling and running Java programs.
- **Eclipse IDE**: Powerful integrated development environment for Java development.
- **JUnit 4**: Popular unit testing framework for Java.

1. **Import the project into Eclipse**:
   - Open Eclipse IDE.
   - Select "File" -> "Import" -> "Existing Maven Projects".
   - Browse to the project directory and select it.
   - Click "Finish".

2. **To run the game**:
   - Run the `Main.java` (src/main/java) file as a Java application.
   - Right-click on `Main.java` class => Run as => select Java Application.

### How to Play

1. **Player Initialization**: Two players are created with initial attributes (health, strength, and attack).
2. **Turn-Based Combat**: Players take turns attacking and defending.
3. **Dice Rolls**: Each player rolls a 6-sided die for attack and defense.
4. **Damage Calculation**: Damage is calculated based on the dice rolls and player attributes.
5. **Game End**: The game continues until one player's health reaches 0.

## Unit Tests

Unit tests are provided to ensure the correctness of the code. JUnit 4 and Hamcrest libraries are used for testing.

### Steps to Run Unit Tests

1. Right-click on the testing class.
2. Select "Run as" => "JUnit Test Case".

