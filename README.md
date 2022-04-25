# CPM / PERT
![PERT](https://upload.wikimedia.org/wikipedia/commons/b/b9/Pert_chart_colored.gif)
#### CPM(Critical Path Method, CPM)
...
#### PERT
...
</br>
#### Progress Status
- Create Node[O]
- Graph Visualization[O]
    - Node can be placed automatically.
    - Links are created automatically.
- CPM
    - Forward calculation[O]
    - Backward calculation[...}
- PERT
    - Time calculation[...]
    - Forward calculation[...]
    - Backward calculation[...]

- Interface?
    - Node Information Input
- 코드 정리...

※ Input Variable
![input](https://user-images.githubusercontent.com/44805829/165007723-454d6b2c-6fc8-4884-8bec-a21c11b44323.png)

### Example1

```python
# Node Information
node_map = [[1,2,3],[4],[6],[5],[8],[7],[8],[8],[9],[]]
node_weight_map = [[[1,1],[2,2],[3,3]],[[4,1]],[[6,6]],[[5,7]],[[8,1]],[[7,3]],[[8,9]],[[8,3]],[[9,10]],[]]
virtual_link=[[1,2]]
# Create Node
grp = dir_graph_pert(node_map = node_map,node_weight_map=node_weight_map,virtual_link=virtual_link)
# Forward Calc.
grp.forward_calc()

# Node Graph
grpplt = plot_node_graph(node_map=node_map,node_weight_map=node_weight_map,virtual_link=[[1,2]])
# Node location arrangement
grpplt.calc_col_row()

# Plot
grpplt.node_plotting()
grpplt.arrow_plotting()
grpplt.virtual_arrow()
grpplt.weight_plotting()
grpplt.forward_plotting(grp.forward_value)
grpplt.drawing()
```

![graph1](https://user-images.githubusercontent.com/44805829/165005520-fe241462-a364-4aa3-9a6a-e1143dc70b5c.png)

### Example2
```python
# Node Information
node_map = [[1,2],[3],[3],[]]
node_weight_map = [[[1,10],[2,7]],[[3,6]],[[3,8]],[]]
virtual_link = [[1,2]]
# Create Node
grp = dir_graph_pert(node_map = node_map,node_weight_map=node_weight_map,virtual_link=virtual_link)
# Forward Calc.
grp.forward_calc()

# Node Graph
grpplt = plot_node_graph(node_map=node_map,node_weight_map=node_weight_map,virtual_link=[[1,2]])
# Node location arrangement
grpplt.calc_col_row()

# Plot
grpplt.node_plotting()
grpplt.arrow_plotting()
grpplt.virtual_arrow()
grpplt.weight_plotting()
grpplt.forward_plotting(grp.forward_value)
grpplt.drawing()
```
![graph2](https://user-images.githubusercontent.com/44805829/165005536-12b2ff1a-23e1-4363-95fe-ecdb27818530.png)
