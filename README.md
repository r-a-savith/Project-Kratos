# Project-Kratos
Overview
The simulation consists of three classes:
Position: Represents coordinates and traversability.
Map: A 2D grid composed of Position objects.
Rover: Simulates rover movement and battery usage.

Class Descriptions
class Position
Represents a location on the map.

Attributes:
x (int) – X-coordinate.
y (int) – Y-coordinate.

traversable (bool) – Indicates if the rover can move through this position.

Methods:
__eq__ and __hash__ – Allow Position to be used in sets and compared for equality.

class Map
Creates a 2D grid of Position objects.

Attributes:
rows (int) – Number of rows in the grid.
cols (int) – Number of columns in the grid.
grid (2D list of Position) – The terrain layout.

Methods:
is_valid(x, y) – Returns True if (x, y) is within bounds and traversable.
get_position(x, y) – Returns the Position object at (x, y).

class Rover
Simulates a rover that moves through the map, starting with 100% battery.

Attributes:
battery (int) – Current battery level (starts at 100%).
current_position (Position) – The rover’s current location.

Methods:
traverse(map_obj, target_pos):
Attempts to move the rover from its current position to target_pos.
Only allows up/down/left/right moves (no diagonals).
Uses BFS to find the shortest path.
Battery usage is 1% per step.
Returns: Number of steps taken, or -1 if path is blocked or insufficient battery.

