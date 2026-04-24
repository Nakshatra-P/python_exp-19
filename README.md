# Experiment 19: Advanced and Interactive Data Visualization Techniques

## Aim:

To study and implement advanced and interactive visualization techniques such as treemaps, dendrograms, Venn diagrams, Sankey diagrams, 3D scatter plots, and radar charts using Plotly and Matplotlib libraries in Python.

---

## Theory:

### 1. Treemap

```python
import pandas as pd
import plotly.express as px

df = pd.DataFrame({
    'Department': ['HR', 'Finance', 'IT', 'Marketing'],
    'Budget': [20, 35, 50, 25]
})

fig = px.treemap(
    df,
    path=['Department'],
    values='Budget',
    title='Department Budget Distribution'
)

fig.show()
```

- `import pandas as pd`
  - Imports Pandas library for data handling.

- `import plotly.express as px`
  - Imports Plotly Express module.
  - Used for creating interactive visualizations.

- `pd.DataFrame()`
  - Creates dataset in tabular format.

- `px.treemap()`
  - Creates a treemap visualization.

- `path=['Department']`
  - Defines hierarchical categories.

- `values='Budget'`
  - Determines rectangle sizes based on budget values.

- `title=`
  - Sets title of the graph.

- `fig.show()`
  - Displays the interactive graph.

Treemaps are used to represent hierarchical data using nested rectangles.

---

### 2. Dendrogram

```python
from scipy.cluster.hierarchy import dendrogram, linkage
import matplotlib.pyplot as plt

data = [
    [1, 2],
    [2, 3],
    [3, 4],
    [5, 6]
]

linked = linkage(data, method='ward')

dendrogram(linked)

plt.show()
```

- `from scipy.cluster.hierarchy import dendrogram, linkage`
  - Imports functions for hierarchical clustering.

- `linkage()`
  - Performs hierarchical clustering on dataset.

- `method='ward'`
  - Uses Ward’s method to minimize cluster variance.

- `dendrogram()`
  - Visualizes clustering hierarchy.

- `plt.show()`
  - Displays the graph.

Dendrograms are used in clustering analysis to show relationships between data points.

---

### 3. Venn Diagram

```python
from matplotlib_venn import venn2
import matplotlib.pyplot as plt

A = set([1,2,3,4])
B = set([3,4,5,6])

venn2(
    [A, B],
    set_labels=('Set A', 'Set B')
)

plt.show()
```

- `from matplotlib_venn import venn2`
  - Imports function for creating Venn diagrams.

- `set()`
  - Creates sets of values.

- `venn2()`
  - Creates Venn diagram for two sets.

- `[A, B]`
  - Specifies the sets to compare.

- `set_labels=`
  - Assigns labels to sets.

Venn diagrams are used to represent intersections and relationships between sets.

---

### 4. Sankey Diagram

```python
import plotly.graph_objects as go

fig = go.Figure(data=[
    go.Sankey(
        node=dict(
            label=[
                "Admission",
                "First Year",
                "Second Year",
                "Placed"
            ]
        ),

        link=dict(
            source=[0,1,2],
            target=[1,2,3],
            value=[100,80,60]
        )
    )
])

fig.show()
```

- `import plotly.graph_objects as go`
  - Imports Plotly graph objects module.

- `go.Figure()`
  - Creates figure object.

- `go.Sankey()`
  - Creates Sankey diagram.

- `node=dict()`
  - Defines nodes in diagram.

- `label=[]`
  - Specifies node names.

- `link=dict()`
  - Defines flow connections.

- `source=[]`
  - Defines starting node indices.

- `target=[]`
  - Defines ending node indices.

- `value=[]`
  - Represents quantity flowing between nodes.

Sankey diagrams are used to visualize flow of data, resources, or processes.

---

### 5. 3D Scatter Plot

```python
import plotly.express as px

df = pd.DataFrame({
    'Study_Hours': [2,3,4,5],
    'Marks': [50,60,70,80],
    'Attendance': [65,70,85,90]
})

fig = px.scatter_3d(
    df,
    x='Study_Hours',
    y='Marks',
    z='Attendance'
)

fig.show()
```

- `px.scatter_3d()`
  - Creates a three-dimensional scatter plot.

- `x='Study_Hours'`
  - Sets X-axis values.

- `y='Marks'`
  - Sets Y-axis values.

- `z='Attendance'`
  - Sets Z-axis values.

3D scatter plots help visualize relationships among three variables simultaneously.

---

### 6. Radar Chart

```python
import plotly.graph_objects as go

skills = [
    'Python',
    'Communication',
    'Problem Solving',
    'Creativity',
    'Leadership'
]

values = [8,7,9,6,7]

fig = go.Figure()

fig.add_trace(
    go.Scatterpolar(
        r=values,
        theta=skills,
        fill='toself',
        name='Student Skills'
    )
)

fig.show()
```

- `go.Scatterpolar()`
  - Creates radar chart using polar coordinates.

- `r=values`
  - Defines radial values.

- `theta=skills`
  - Defines category labels around chart.

- `fill='toself'`
  - Fills enclosed polygon area.

- `name='Student Skills'`
  - Assigns label to chart.

- `fig.add_trace()`
  - Adds chart data to figure.

Radar charts are used to compare performance across multiple categories.

---

### 7. Sunburst Chart

```python
fig = px.sunburst(
    df,
    path=['Department'],
    values='Budget'
)

fig.show()
```

- `px.sunburst()`
  - Creates a sunburst chart.

- `path=`
  - Defines hierarchy levels.

- `values=`
  - Determines segment size.

Sunburst charts visualize hierarchical data in circular form.

---

### 8. Funnel Chart

```python
fig = px.funnel(
    df,
    x='Budget',
    y='Department'
)

fig.show()
```

- `px.funnel()`
  - Creates funnel chart.

- `x='Budget'`
  - Defines quantitative values.

- `y='Department'`
  - Defines stages or categories.

Funnel charts visualize reduction through stages in a process.

---

## Conclusion:

Advanced and interactive visualization techniques such as treemaps, dendrograms, Venn diagrams, Sankey diagrams, 3D scatter plots, radar charts, sunburst charts, and funnel charts were successfully implemented using Plotly and Matplotlib libraries. These visualizations helped in representing hierarchical, multidimensional, and flow-based data effectively, making complex datasets easier to analyze and interpret.
