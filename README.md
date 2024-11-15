# THIS-IS-MY-FIRST-GIT-REPO..


// // #include <iostream>
// // #include <vector>  // Include vector header
// // using namespace std;

// // // Define the Node class for a linked list
// // class Node {
// // public:
// //     int data;  // This variable will store the data of the node
// //     Node* next; // This pointer will point to the next node in the list

// //     // Constructor to initialize a node with data and a pointer to the next node
// //     Node(int data1, Node* next1) {
// //         data = data1;  // Set the data of the node
// //         next = next1;  // Set the pointer to the next node
// //     }

// //     // Constructor to initialize a node with data, but no next node (it will be null)
// //     Node(int data1) {
// //         data = data1;  // Set the data of the 
// //         next = nullptr;  // No next node, so set the pointer to 
// //     }
// // };


// // int main() {
// //     // Declare and initialize the vector 'arr' with integers
// //     vector<int> arr = {2, 5, 8, 7};

// //     // Create a new Node using the first element of the vector (arr[0])
// //     Node* y = new Node(arr[3]);

// //     // Output the memory address of the Node (where it's stored in memory)
// //     cout << y << '\n'; // This prints the memory address where the node is located

// //     // Output the data stored in the Node (not the memory address)
// //     cout << y->data << '\n'; // This prints the actual value stored in the node (arr[0] = 2)

// //     return 0;
// // }
// #include <iostream>
// using namespace std;

// // Node structure definition
// struct Node {
//     int data;            // Integer data for the node
//     Node* next;          // Pointer to the next node in the list

//     // Constructor to initialize node data and next pointer
//     Node(int value) : data(value), next(nullptr) {}
// };

// // LinkedList class definition
// class LinkedList {
// private:
//     Node* head;          // Pointer to the first node in the list

// public:
//     // Constructor initializes an empty list with head as nullptr
//     LinkedList() : head(nullptr) {}

//     // Method to add a node at the end of the list
//     void append(int value) {
//         Node* newNode = new Node(value);  // Create a new node with the given value
//         if (head == nullptr) {            // If list is empty, new node becomes the head
//             head = newNode;
//         } else {
//             Node* temp = head;            // Start from the head node
//             while (temp->next != nullptr) // Traverse to the last node
//                 temp = temp->next;
//             temp->next = newNode;         // Link last node to the new node
//         }
//     }

//     // Method to display the list's elements
//     void display() {
//         Node* temp = head;                // Start from the head node
//         while (temp != nullptr) {         // Traverse the list until the end
//             cout << temp->data << " -> "; // Print current node's data
//             temp = temp->next;            // Move to the next node
//         }
//         cout << "nullptr" << endl;        // Indicate end of the list
//     }

//     // Method to insert a node at the beginning of the list
//     void prepend(int value) {
//         Node* newNode = new Node(value);  // Create a new node with the given value
//         newNode->next = head;             // Link new node to current head
//         head = newNode;                   // Update head to the new node
//     }

//     // Method to delete a node with a specific value
//     void deleteValue(int value) {
//         if (head == nullptr) return;      // If list is empty, exit

//         // If head node holds the target value
//         if (head->data == value) {
//             Node* temp = head;            // Store current head in a temp variable
//             head = head->next;            // Move head to the next node
//             delete temp;                  // Delete old head
//             return;
//         }

//         Node* temp = head;                // Start from head node
//         while (temp->next != nullptr && temp->next->data != value) {
//             temp = temp->next;            // Find node just before the target node
//         }

//         if (temp->next == nullptr) return; // Value not found, exit

//         Node* nodeToDelete = temp->next;  // Target node to delete
//         temp->next = nodeToDelete->next;  // Link around target node
//         delete nodeToDelete;              // Free memory for target node
//     }

//     // Destructor to free all nodes when list is destroyed
//     ~LinkedList() {
//         Node* temp;
//         while (head != nullptr) {         // Traverse each node
//             temp = head;                  // Store current head
//             head = head->next;            // Move head to the next node
//             delete temp;                  // Delete old head node
//         }
//     }
// };

// int main() {
//     LinkedList list;             // Create a new linked list

//     list.append(10);             // Append nodes to the list
//     list.append(20);
//     list.append(30);
//     list.display();              // Display current list: 10 -> 20 -> 30 -> nullptr

//     list.prepend(5);             // Prepend a node to the list
//     list.display();              // Display updated list: 5 -> 10 -> 20 -> 30 -> nullptr

//     list.deleteValue(20);        // Delete node with value 20
//     list.display();              // Display updated list: 5 -> 10 -> 30 -> nullptr

//     list.deleteValue(5);         // Delete node with value 5 (the head)
//     list.display();              // Display updated list: 10 -> 30 -> nullptr

//     return 0;
// }





#include <iostream>
using namespace std;      




































// Step 1: Node structure banate hain
struct Node {
    int data;       // Data part jo value hold karega
    Node* next;     // Pointer part j o next node ka address store karega

    // Constructor to initialize a node
    Node(int value) {
        data = value;
        next = nullptr;  // Initially, next nullptr set karte hain
    }
};

// Step 2: Ek function to insert a new node at the end of the linked list
void insertAtEnd(Node*& head, int value) {
    Node* newNode = new Node(value);  // Nayi node create ki
    
    // Agar list empty hai, toh yeh node hi head ban jati hai
    if (head == nullptr) {
        head = newNode;
        return;
    }
    
    // Agar list mein already nodes hain, toh last node tak pahunchte hain
    Node* temp = head;
    while (temp->next != nullptr) {
        temp = temp->next;
    }
    // there are several of that nodes which is 
    // Last node ke next pointer mein nayi node ka address daalte hain
    temp->next = newNode;
}

// Step 3: Display function to print all nodes
void display(Node* head) {
    Node* temp = head;
    while (temp != nullptr) {
        cout << temp->data << " -> ";
        temp = temp->next;
    }
    cout << "nullptr" << endl;
}

int main() {
    Node* head = nullptr;  // Linked List ka head initially nullptr hai

    // Linked List mein kuch values add karte hain
    insertAtEnd(head, 10);
    insertAtEnd(head, 20);
    insertAtEnd(head, 30);
    insertAtEnd(head, 40);
    insertAtEnd(head, 40);
    insertAtEnd(head, 40);
       
  

    // Display the linked list
    display(head);  // Output: 10 -> 20 -> 30 -> 40 -> nullptr
    
    return 0;
}
