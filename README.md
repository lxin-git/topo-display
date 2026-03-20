# Topology Visualization Tool

An interactive web-based topology visualization tool for displaying network topology data from JSON files.

## Features

- 🌐 **Interactive Graph Visualization**: Display nodes and edges in an interactive force-directed graph
- 🎨 **Color-Coded Nodes**: Different plugin types are automatically color-coded for easy identification
- 🔍 **Smart Search**: Search nodes by label, plugin type, or ID with automatic highlighting and centering
- 📄 **JSON Data Viewer**: View the raw JSON data in a side panel
- 📊 **Statistics Display**: Real-time display of node and edge counts
- 🔄 **Zoom & Pan**: Interactive zoom and pan controls for exploring large topologies
- 💡 **Tooltips**: Hover over nodes to see detailed information
- 🎯 **Drag & Drop**: Drag nodes to rearrange the layout
- 📱 **Responsive Design**: Works on different screen sizes

## How to Use

1. **Open the Application**
   - Open `index.html` in a modern web browser (Chrome, Firefox, Safari, or Edge)

2. **Load Your Topology Data**
   - Click the "📁 Load JSON File" button
   - Select your JSON file (e.g., `topo-xstan.json`)
   - The topology will be automatically rendered

3. **Interact with the Visualization**
   - **Pan**: Click and drag on the background to move the view
   - **Zoom**: Use the zoom controls (+, −, ⊙) in the bottom-right corner or mouse wheel
   - **Move Nodes**: Click and drag individual nodes to reposition them
   - **View Details**: Hover over any node to see its detailed information
   - **Search**: Type in the search box to find nodes - matched nodes will be highlighted and automatically centered
   - **View JSON**: Click "📄 Show JSON Data" to view the raw JSON in a side panel
   - **Reset View**: Click "🔄 Reset View" to clear search and return to the default view
   - **Clear**: Click "🗑️ Clear" to remove the current visualization

## JSON File Format

The tool expects JSON files with the following structure:

```json
{
  "nodes": [
    {
      "id": "unique-node-id",
      "plugin": "pluginType",
      "label": "Node Label",
      "entityId": {
        "host": "hostname",
        "pluginId": "plugin.identifier",
        "steadyId": "steady-identifier"
      }
    }
  ],
  "edges": [
    {
      "source": "source-node-id",
      "destination": "destination-node-id",
      "relation": "relationship-type"
    }
  ]
}
```

### Required Fields

**Nodes:**
- `id`: Unique identifier for the node
- `plugin`: Plugin type (used for color coding)
- `label`: Display name for the node
- `entityId`: Object containing host, pluginId, and steadyId

**Edges:**
- `source`: ID of the source node
- `destination`: ID of the destination node
- `relation`: Type of relationship between nodes

## Example Usage

1. The repository includes a sample file `topo-xstan.json` with topology data
2. Open `index.html` in your browser
3. Click "Load JSON File" and select `topo-xstan.json`
4. Explore the visualization using the interactive controls

## Technical Details

- **Built with**: HTML5, CSS3, JavaScript (ES6+)
- **Visualization Library**: D3.js v7
- **Layout Algorithm**: Force-directed graph layout
- **No Server Required**: Runs entirely in the browser as a static page

## Browser Compatibility

- ✅ Chrome/Edge (recommended)
- ✅ Firefox
- ✅ Safari
- ⚠️ Internet Explorer (not supported)

## Tips for Large Topologies

- Use the search function to quickly locate and focus on specific nodes
- Search results are automatically highlighted and centered in the view
- Adjust zoom level for better overview
- Drag nodes to untangle complex connections
- The force simulation will automatically organize nodes for optimal viewing
- Use the JSON viewer to inspect the raw data structure

## Legend

The legend in the top-right corner shows all plugin types present in your topology data, each with its assigned color.

## Performance

The tool can handle topologies with thousands of nodes and edges. For very large datasets (10,000+ nodes), initial rendering may take a few seconds.

---

**Note**: This is a client-side application. All data processing happens in your browser, and no data is sent to any server.
