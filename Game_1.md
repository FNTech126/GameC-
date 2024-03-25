# GameC++

#include <iostream>

using namespace std;

// Class representing the player character
class Player {
private:
    int x;
    int y;

public:
    Player() : x(0), y(0) {}

    void moveUp() {
        y--;
    }

    void moveDown() {
        y++;
    }

    void moveLeft() {
        x--;
    }

    void moveRight() {
        x++;
    }

    void displayPosition() {
        cout << "Player is at position (" << x << ", " << y << ")" << endl;
    }
};

// Function to display game instructions
void displayInstructions() {
    cout << "Welcome to the Simple Game!" << endl;
    cout << "Use 'W' to move up, 'S' to move down, 'A' to move left, and 'D' to move right." << endl;
    cout << "Press 'Q' to quit." << endl;
}

int main() {
    char choice;
    Player player;

    displayInstructions();

    do {
        player.displayPosition();

        cout << "Enter your move: ";
        cin >> choice;

        switch (choice) {
            case 'W':
            case 'w':
                player.moveUp();
                break;
            case 'S':
            case 's':
                player.moveDown();
                break;
            case 'A':
            case 'a':
                player.moveLeft();
                break;
            case 'D':
            case 'd':
                player.moveRight();
                break;
            case 'Q':
            case 'q':
                cout << "Quitting the game. Goodbye!" << endl;
                return 0;
            default:
                cout << "Invalid choice. Please try again." << endl;
        }
    } while (true);

    return 0;
}
