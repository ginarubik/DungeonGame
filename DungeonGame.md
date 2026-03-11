Dungeon Game – Code Documentation Questions 1-3

1.Every monster's every data: health points, damage type, damage, damage resistance (from which type of damage it has a reduction and what percentage), what's it's special variable, 
what's it's eating and what does it do

2.Every hero class' every data: health points, damage type, damage, damage reduction to flying enemies, damage resistance and what's it yelling when somebody levelled up

3.How many monsters in the dungeon and what type are they?


1. Monsters:

Beholder

Health Points: 50

Damage: 10

Damage Type: EYE_RAY

Damage Resistance

No damage reduction.

Special Variable

eyes (initial value: 10)

Special Mechanic
When the Beholder takes damage, the number of eyes decreases by damage / 10.
If the number of eyes becomes 0 or less, the Beholder dies immediately.

What It Eats

A whole goblin.

Eating Effect

Restores 20 health points.

Action

The Beholder stares with all of its eyes.

Dragon

Health Points: 60

Damage: 8

Damage Type: MAGIC

Damage Resistance

Damage Type	Reduction
MAGIC	40%
SLASHING	20%
EYE_RAY	None

Special Variable

color (defines the dragon type).

What It Eats

Food from its treasure hoard.

Eating Effect

Restores 30 health points.

Increases damage by 1.

Action

The dragon counts its gold.

Orc

Health Points: 30

Damage: 5

Damage Type: SLASHING

Damage Resistance

Damage Type	Reduction
SLASHING	20%
Others	None

Special Ability

hitWallWithHead()
The Orc hits a wall with its head and loses 10 health points.

What It Eats

A mayonnaise sandwich.

Eating Effect

Restores 10 health points.

Action

The Orc counts the heads it has collected.

Skeleton

Health Points: 20

Damage: 3

Damage Type: SLASHING

Damage Resistance / Weakness

Damage Type	Effect
MAGIC	20% more damage
Others	Normal damage

Special Variable

None.

What It Eats

Skeletons do not eat.

Action

The skeleton plays on its bones like a xylophone.

2. Hero Classes

Hero attributes are modified by race modifiers.

Race	Health Modifier	Damage Modifier
HUMAN	1.0	1.0
ELF	0.8	1.2
DWARF	1.2	0.8
Barbar

Base Health: 20

Damage: 8

Damage Type: SLASHING

Damage Reduction to Flying Enemies

Deals 50% damage to flying enemies.

Flying enemies include:

Dragon

Beholder

Damage Resistance

Damage Type	Reduction
SLASHING	20%

Level-Up Yell

Wraaaaaargh!
Bard

Base Health: 15

Damage: 10

Damage Type: SLASHING

Damage Reduction to Flying Enemies

None.

Damage Resistance

Damage Type	Reduction
All types	20%

Level-Up Yell

Tralla-lalla-lalla-la
Wizard

Base Health: 18

Damage: 15

Damage Type: MAGIC

Damage Reduction to Flying Enemies

None.

Damage Resistance

Damage Type	Reduction
MAGIC	20%

Level-Up Yell

You can't even understand the magic I use on a daily basis you dumbass!

3. Monsters in the Dungeon

The dungeon contains monsters stored in a list in the Dungeon class.

Possible monster types:

Beholder

Dragon

Orc

Skeleton

Important rules:

The first monster in the list is always the one fighting the hero.

When a monster dies, it is removed from the list.

The number of monsters in the dungeon equals the size of the monster list.

4. Additional Observations

Some small issues were identified in the code:

Bard shortcut bug – the menu says Bd, but the code checks "db".

Typos in some printed messages (e.g., "xelofon").

heroes.get(0) and monsters.get(0) could cause IndexOutOfBoundsException if lists are empty.

The Beholder eye mechanic may kill the monster instantly even with remaining health.

Only the first hero fights, while other heroes wait until the current one dies.

