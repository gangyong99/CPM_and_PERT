# CPM / PERT
![PERT](https://upload.wikimedia.org/wikipedia/commons/b/b9/Pert_chart_colored.gif)
#### CPM(Critical Path Method)
...
#### PERT(Program/Project Evaluation and Review Technique)
...
</br>
#### Progress Status
- Create Node[O]
- Graph Visualization[O]
    - Node can be placed automatically.
    - Links are created automatically.
- CPM
    - Forward calculation[O]
    - Backward calculation[O]
    - Critical Path[...]
- PERT
    - Time calculation[...]
    - Forward calculation[...]
    - Backward calculation[...]
    - Critical Path[...]
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
grp.backward_calc()

# Node Graph
grpplt = plot_node_graph(node_map=node_map,node_weight_map=node_weight_map,virtual_link=virtual_link)
# Node location arrangement
grpplt.calc_col_row()

# Plot
grpplt.node_plotting()
grpplt.arrow_plotting()
grpplt.virtual_arrow()
grpplt.weight_plotting()
grpplt.time_plotting(grp.forward_value,grp.backward_value)
grpplt.drawing()
```
![graph1](https://user-images.githubusercontent.com/44805829/165019057-cd5105dd-3530-4b9a-9671-170cfd94f988.png)

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
grp.backward_calc()

# Node Graph
grpplt = plot_node_graph(node_map=node_map,node_weight_map=node_weight_map,virtual_link=virtual_link)
# Node location arrangement
grpplt.calc_col_row()

# Plot
grpplt.node_plotting()
grpplt.arrow_plotting()
grpplt.virtual_arrow()
grpplt.weight_plotting()
grpplt.time_plotting(grp.forward_value,grp.backward_value)
grpplt.drawing()
```
![graph2](https://user-images.githubusercontent.com/44805829/165019080-e2782ec3-c490-49c8-a2b4-b676ee1f076a.png)

### Example3
```python
# Node Information
node_map = [[1,2,3],[4],[6],[5],[8],[7],[8],[8],[9],[]]
node_weight_map = [[[1,4],[2,4],[3,5]],[[4,5]],[[6,5]],[[5,2]],[[8,6]],[[7,2]],[[8,3]],[[8,4]],[[9,5]],[]]
virtual_link = [[2,3],[5,6]]
grp = dir_graph_pert(node_map = node_map,node_weight_map=node_weight_map,virtual_link=virtual_link)
grp.forward_calc()
grp.backward_calc()

# Node Graph
grpplt = plot_node_graph(node_map=node_map,node_weight_map=node_weight_map,virtual_link=virtual_link)
# Node location arrangement
grpplt.calc_col_row()

# Plot
grpplt.node_plotting()
grpplt.arrow_plotting()
grpplt.virtual_arrow()
grpplt.weight_plotting()
grpplt.time_plotting(grp.forward_value,grp.backward_value)
grpplt.drawing()
```
![graph3](https://user-images.githubusercontent.com/44805829/165019116-b2af4d2f-f69d-4bc2-8149-06e38a71193e.png)
