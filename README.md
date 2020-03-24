# Forest
A simple forest simulator.

## Rules
The forest is laid out as a grid.  Plants and animals are distributed randomly throughout the grid.

**Animals** have properties: 
    - `food source` - This can be `herbivore`, `carnivore`, or `omnivore`.
    - `hunger` - Can be `hungry` or `not hungry`.
    - `life` - Tracks the health of the animal.

All animals start with a random food preference, a hunger of `not hungry`, and a full life.

**Plants** have properties: 
    - `life` - Tracks the health of the plant.

At every iteration of the simulation:

1. For herbivorous animals:
    1. When hungry and next to a plant, the animal will eat from the plant, reducing the plant's life by the amount needed to restore full life to the animal.
    2. Does not eat animals.
2. For carnivorous animals:
    1. When hungry and next to another animal, the animal will eat the other animal, reducing the other animal's life by the amount needed to restore full life to the animal.
    2. Does not eat plants.
3. For omnivorous animals, herbivorous and carnivorous rules apply.
4. For all animals:
    1. The animal will move one grid position in any of the 8 directions around it (N, S, E, W, NE, NW, SE, or SW).
    2. Life is reduced by one if it does not eat.  If no life remains, the animal is considered dead.
    3. The animal is hungry if its life is not full.
    4. The animal will eat only if it is hungry and next to food.
5. For plants:
    1. Life is unchanged if it is full.
    2. Life is reduced by one if it is less than half.
    3. Life is increased by one if is half or more.

Other requirements:
- Periodically, the forest must be culled of dead plants and animals.
