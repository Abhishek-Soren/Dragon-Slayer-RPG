# Dragon Slayer RPG

Overview
--------

**Dragon Slayer RPG** is a browser-based RPG game where players must defeat a dragon to save a town. The game involves navigating different locations, fighting various monsters, managing resources like health and gold, and upgrading weapons.

Game Features
-------------

### Game Statistics

-   **XP**: Tracks experience points earned by defeating monsters.
-   **Health**: Represents the player's health. The game ends if it reaches zero.
-   **Gold**: Currency used to purchase health and weapons.

### Controls

-   **Navigation Buttons**: Allow players to move between different locations such as the town square, store, and cave.
-   **Action Buttons**: Used during fights to attack, dodge, or run away.

### Locations

1.  **Town Square**: Starting point with options to go to the store, cave, or fight the dragon.
2.  **Store**: Players can buy health or weapons with gold.
3.  **Cave**: Contains different monsters to fight for XP and gold.
4.  **Fight Scene**: Where battles with monsters take place.
5.  **Kill Monster Scene**: Displays after defeating a monster, allowing players to collect rewards.
6.  **Lose Scene**: Displays when the player's health reaches zero.
7.  **Win Scene**: Displays when the player defeats the dragon.
8.  **Easter Egg Scene**: A secret mini-game with a guessing element.

### Monsters

-   **Slime**: Low-level monster with minimal health.
-   **Fanged Beast**: Medium-level monster with moderate health.
-   **Dragon**: High-level monster with substantial health.

### Weapons

-   **Stick**: Basic weapon with minimal power.
-   **Dagger**: Upgraded weapon with increased power.
-   **Claw Hammer**: More powerful weapon.
-   **Sword**: Most powerful weapon in the game.

Game Mechanics
--------------

### Initialization

-   The game starts by initializing XP, health, gold, and the player's current weapon. Inventory is set to the basic weapon (stick).

### Functions

#### Navigation and Updates

-   **update(location)**: Updates the game interface based on the current location. This includes changing button texts and functions, updating the descriptive text, and hiding/showing monster statistics.
-   **goTown()**: Navigates to the town square.
-   **goStore()**: Navigates to the store.
-   **goCave()**: Navigates to the cave.
-   **goFight()**: Navigates to the fight scene and initializes the monster's health and stats.

#### Store Actions

-   **buyHealth()**: Allows players to purchase health if they have enough gold.
-   **buyWeapon()**: Allows players to purchase a weapon upgrade if they have enough gold and haven't already acquired the most powerful weapon.
-   **sellWeapon()**: Allows players to sell their current weapon for gold, provided they have more than one weapon in their inventory.

#### Combat

-   **fightSlime()**: Initiates a fight with a slime.
-   **fightBeast()**: Initiates a fight with a fanged beast.
-   **fightDragon()**: Initiates a fight with the dragon.
-   **attack()**: Handles the attack action during a fight. The player attacks the monster, and the monster counterattacks. Updates health and monster health accordingly. Includes a random chance of breaking a weapon.
-   **dodge()**: Handles the dodge action during a fight, allowing the player to avoid an attack.

#### Post-Combat

-   **defeatMonster()**: Handles the aftermath of defeating a monster, awarding XP and gold.
-   **lose()**: Displays the lose scene when the player's health reaches zero.
-   **winGame()**: Displays the win scene when the player defeats the dragon.
-   **restart()**: Resets the game to the initial state.

#### Easter Egg Mini-Game

-   **easterEgg()**: Navigates to the easter egg scene.
-   **pickTwo()**: Picks the number 2 in the mini-game.
-   **pickEight()**: Picks the number 8 in the mini-game.
-   **pick(guess)**: Handles the mini-game logic. Randomly generates ten numbers and checks if the player's guess matches any of them, awarding gold or deducting health accordingly.

Detailed Function Descriptions
------------------------------

### update(location)

This function updates the game interface based on the provided location object. It changes the text and actions of the buttons, updates the descriptive text, and hides the monster stats if not in a fight.

### goTown()

Sets the game state to the town square. The town square allows the player to go to the store, the cave, or directly to fight the dragon.

### goStore()

Sets the game state to the store. In the store, players can buy health or weapons if they have enough gold.

### goCave()

Sets the game state to the cave. The cave contains monsters that players can choose to fight.

### buyHealth()

Allows the player to buy 10 health points for 10 gold. If the player does not have enough gold, a message is displayed.

### buyWeapon()

Allows the player to buy the next weapon in the list for 30 gold. If the player already has the most powerful weapon or doesn't have enough gold, appropriate messages are displayed. If the player already has the most powerful weapon, the option to sell the weapon is provided.

### sellWeapon()

Allows the player to sell their current weapon for 15 gold, provided they have more than one weapon in their inventory.

### fightSlime(), fightBeast(), fightDragon()

These functions set the state to a fight with the corresponding monster. They call `goFight()` with the appropriate monster data.

### goFight()

Sets the game state to the fight scene, initializes the monster's health, and updates the monster stats section with the current monster's details.

### attack()

Handles the player's attack action. It calculates damage based on the player's weapon and XP, and also handles the monster's counterattack. It updates both the player's and the monster's health, checks for win/lose conditions, and handles the random chance of weapon breakage.

### dodge()

Handles the player's dodge action, allowing them to avoid the monster's attack.

### defeatMonster()

Handles the aftermath of defeating a monster. It awards gold and XP to the player, updates the interface, and sets the state to the "kill monster" scene.

### lose()

Sets the game state to the "lose" scene, displaying a message that the player has died.

### winGame()

Sets the game state to the "win" scene, displaying a message that the player has defeated the dragon and won the game.

### restart()

Resets all game variables to their initial states and sets the game state back to the town square, effectively restarting the game.

### easterEgg()

Sets the game state to the easter egg scene, where the player can participate in a guessing mini-game.

### pickTwo(), pickEight()

These functions call `pick(guess)` with the number 2 or 8, respectively.

### pick(guess)

Handles the easter egg mini-game. It generates ten random numbers and checks if the player's guess matches any of them. If the guess is correct, the player wins gold; if not, they lose health. It also checks for the lose condition if health drops to zero.

Additional Details
------------------

-   **Weapons and Monsters**: Defined in arrays with properties such as name, power, level, and health. This allows easy addition or modification of game content.
-   **Health and Gold Management**: Functions are designed to manage the player's health and gold, providing feedback when actions can't be performed due to insufficient resources.
-   **Random Elements**: Incorporated in combat (e.g., weapon breaks, random numbers in the mini-game) to add unpredictability and challenge.

This project provides a solid foundation for an engaging text-based RPG, with opportunities for further enhancements such as new locations, more monsters, and additional game mechanics.
