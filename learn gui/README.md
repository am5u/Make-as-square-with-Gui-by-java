# Square Puzzle Solver with Multi-threading

A Java-based application that solves square puzzles using a multi-threaded approach with a graphical user interface. The program attempts to fit various pieces into a square board while visualizing the solving process in real-time.

## Features

### Multi-threading Implementation
- Utilizes multiple worker threads to solve the puzzle concurrently
- Each thread explores different piece combinations and rotations
- Thread synchronization to prevent conflicts during solution finding
- Real-time UI updates using SwingUtilities.invokeLater()

### Graphical User Interface
- Interactive 4x4 board visualization
- Color-coded pieces for easy distinction
- Status updates showing solving progress
- Smooth animations during piece placement
- Real-time board state visualization

### Core Algorithms

#### 1. Backtracking Algorithm
The main solving algorithm uses backtracking with the following steps:
- Recursively tries to place pieces on the board
- For each piece:
  - Attempts all possible rotations (0°, 90°, 180°, 270°)
  - Tries all possible positions on the board
  - Validates piece placement
  - Continues with remaining pieces if placement is valid
  - Backtracks if no solution is found

#### 2. Piece Rotation Algorithm
- Implements matrix rotation for piece orientation
- Supports 90-degree rotations
- Preserves piece integrity during transformation

#### 3. Board Management
- Efficient board state tracking
- Piece placement validation
- Collision detection
- State rollback capabilities

## Technical Details

### Threading Architecture
- Main thread handles UI and user interactions
- Worker threads (`WorkerThread.java`) execute solving algorithms
- Thread-safe solution tracking
- Synchronized board updates

### Board Representation
- 4x4 grid (-1 represents empty cells)
- Pieces represented as 2D integer arrays
- Color mapping for visual representation

### Performance Features
- Configurable delay between moves (DELAY constant)
- Piece shuffling for randomized attempts
- Early termination when solution is found

## Usage

1. Run the application
2. The solver will automatically start with multiple threads
3. Watch as the algorithm attempts different combinations
4. Solution status will be displayed when complete

## Implementation Details

### Key Classes
- `Make_asquare.java`: Core solving algorithm and board management
- `WorkerTread.java`: Thread implementation for parallel solving
- `SquareGui.java`: Graphical user interface implementation

### Key Methods
- `Solution()`: Main recursive solving algorithm
- `CanPutPiece()`: Validates piece placement
- `rotatePiece()`: Handles piece rotation
- `UpdaateBoard()`: Manages UI updates

## Dependencies
- Java Swing for GUI
- Java AWT for graphics
- Java Threading utilities 