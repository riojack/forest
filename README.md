# Forest
A simple forest simulator.

### Rules
Initially, the forest starts with a random distribution of plants and animals at various levels of age.

The **forest ecosystem** has properties: 
    - `day`
    - `season`
    
The forest ecosystem starts at day 0 and the season is "Spring".  A year is 40 days long.

**Animals** have properties: 
    - `food source` - This can be `herbivore`, `carnivore`, or `omnivore`.
    - `age`
    - `hunger` - Defaults to 0.  (Possible values: 0 (not hungry), 1 (hungry), 2 (ravenous))
    - `life` - Defaults to 10. (Min: 0; Max: 10)

All animals start with an age of 0, a random food preference, a hunger of 0, and a life of 10.

**Plants** have properties: 
    - `age`
    - `growth speed`
    - `life`


At every iteration of the simulation:

1. The forest ecosystem:
    1. If the day is 39, set day to zero; else increment the day by 1.
    2. Between days 0-9, it is Spring.  Between days 10-19, it is Summer. Between days 20-29, it is Fall.  Between days 30-39, it is Winter.
2. Animals:
    1. If the age is 79, set life to 0; else increment age by 1.
    2. If hunger 