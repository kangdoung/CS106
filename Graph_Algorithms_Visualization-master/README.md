# Graph-Algorithms-Visualization
CS212 Data Structures HW. An API for directed-weighted graph and a GUI visualization for Graph algorithms(BFS, DFS, and Dijkstra).

**Video demo:**
[![GraphAlgos](https://i.imgur.com/LG1ZJ8f.png)](https://www.youtube.com/watch?v=reVHJi7VOMQ)

**Graph.java**: This is an implementation of direct weighted Graph, with two nested classes Node and Edge. In order to ensure the representational flexibility, the Graph class is generic parameterized by two types. This class includes a check function, several graph algorithm, and accessors and manipulators of data in a graph. 

**GraphTest.java**: This is a checking and debugging tool for Graph.java. The test checks the consistency of the graph before and after revising, BFS, DFS and Dijkstra, and ensure the Dijkstra algorithm finds the shortest path after a directed flight between two cities is added.

**NodeData.java and EdgeData.java**: These are two customized classes designed for GUI displaying purposes (keeping the Graph class and its nested classes generic and flexible). They store GUI-based data of a node or an edge (position, color, text and distance) and provide corresponding accessors and manipulators.

**GraphCanvas.java**: This class acts like the View class in the Model-View-Controller model. It requests information from the Graph, NodeData and EdgeData as needed to paint components and create a display. It can also change data in NodeData and EdgeData based on the request from the Controller class GraphGUI. The paintArrowLine method is a worker method for drawing an arrow, which utilizes trigonometric function to calculate endpoints of an arrow. The paintTraversal method paints edges and nodes according to the order given by a traversal algorithm, creates an animative effect using different colors and Thread.sleep(), and returns whether a painted path exists or not for the Thread to check. The refresh method repaints everything in its default color, which can ensure the accurate display of another traversals.

**GraphGUI.java**: This class acts like the Controller class in the Model-View-Controller model. It includes nested classes that define the input modes, action listeners and the Thread. It has several buttons that let user to manipulate the graph and run graph algorithms. Once a button is clicked, the mouse listener will only response to the case in its corresponding mode. A jump window will pump up to let the user change text on a node and weighted distance on an edge. The try-catch clause ensures that the program doesn’t crash when the user enters an invalid input, and makes a beep sound to notify. The Thread is used to control the animation. It disables all those buttons while an animation is running, and enables the refresh button after the animation end.
