## How to use gmsh/meshio:

#### Installation
gmsh: `sudo apt install gmsh`
meshio: `pip install meshio[all]


#### Loading a mesh
```python
import meshio
mesh = meshio.read("<your_file>.msh")
```

#### Getting the surface triangles
```python
# this makes an Nx3 matrix of the vertices in each triangle
# the vertices can index `mesh.points` to get the vertex coordinates
triangles = np.concatenate([ cell.data for cell in mesh.cells if cell.type == "triangle"])
```

#### Writing gmsh files
```python
mesh.write("<your_file>.msh",file_format="gmsh22")
```

for more detail check out [meshio](https://github.com/nschloe/meshio), [pyvista](https://docs.pyvista.org/version/stable/), and [gmsh](https://gitlab.onelab.info/gmsh/gmsh)
