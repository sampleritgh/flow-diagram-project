# flow-diagram-project
Created with CodeSandbox
Dynamic Diagram Flow Application
This documentation explains the architecture setup, application usage, and provides a sample metadata JSON file to demonstrate how to structure nodes and edges.

1. Architecture Setup
1.1. Core Components
React Flow:
A library for creating interactive diagrams.
Handles rendering of nodes and edges and supports dynamic updates.
React Context API:
Manages the application state for nodes and edges.
Allows adding, editing, and deleting nodes and edges seamlessly.
Dynamic Metadata:
The application uses a metadata JSON file as input to define the structure of nodes and edges.
1.2. Project Structure
   
src/
├── App.js             // Main component rendering the diagram and controls
     
├── styles.css         // Application styling
├── context/
│   ├── DiagramContext.js  
├── index.js           // Entry point for React app
└── components/
    ├── DiagramFlow.js     // Component rendering the React Flow diagram
    ├── Sidebar.js 
      
2. Application Usage
2.1. Starting the Application
Clone the repository and navigate to the project directory.
Install dependencies:

npm install
Start the application:

npm start
Open the app in your browser at http://localhost:3000.
2.2. Features
Add Nodes
Input a node label in the "New Node Label" field.
Click the Add Node button.
The new node will appear in the diagram.
Add Edges
Input the source node ID and target node ID in the respective fields.
Optionally, input an edge label.
Click the Add Edge button.
The new edge will connect the specified nodes.
Edit Nodes
Click on a node in the diagram.
Use the sidebar to update the label or position.
Changes will reflect dynamically.
Edit Edges
Click the Edit Edge button.
Provide the edge ID (e.g., e1-2) and update the source, target, or label as prompted.
The diagram updates with the new edge details.
Delete Nodes or Edges
Select a node or edge in the diagram.
Press the Delete button in the sidebar to remove it.
3. Sample Metadata JSON
Below is an example of how to structure the metadata for nodes and edges.

metadata.json
json

{
  "nodes": [
    {
      "id": "1",
      "type": "input", 
      "data": { "label": "Start Node" },
      "position": { "x": 100, "y": 50 }
    },
    {
      "id": "2",
      "type": "default",
      "data": { "label": "Process Node" },
      "position": { "x": 300, "y": 150 }
    },
    {
      "id": "3",
      "type": "output",
      "data": { "label": "End Node" },
      "position": { "x": 500, "y": 250 }
    }
  ],
  "edges": [
    {
      "id": "e1-2",
      "source": "1",
      "target": "2",
      "label": "Start to Process"
    },
    {
      "id": "e2-3",
      "source": "2",
      "target": "3",
      "label": "Process to End"
    }
  ]
}

useEffect(() => {
  setNodes(metadata.nodes);
  setEdges(metadata.edges);
}, []);
Diagram Visualization
Using the sample metadata:

4. Extending the Application
Dynamic Node Types:
Add different node types (e.g., decision nodes, conditional nodes).
Styling:
Customize node/edge styles in styles.css.

