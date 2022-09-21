clear all
N=input('N:');
mu=input('mu:');
gen_mesh_rectangle(N,N,-1,1,-1,1);
elem_vertices=load('elem_vertices.txt');
vertex_coordinates=load('vertex_coordinates.txt');
dirichlet=load('dirichlet.txt');
h=1/N

n_vertices=size(vertex_coordinates,1);
n_elem=size(elem_vertices,1);

for el=1:n_elem
  T=elem_vertices(el,:);
  v1=vertex_coordinates(T(1),:)';
  v2=vertex_coordinates(T(2),:)';
  v3=vertex_coordinates(T(3),:)';
  x1=v1(1);
  y1=v1(2);
  x2=v2(1);
  y2=v2(2);
  x3=v3(1);
  y3=v3(2);
  %Armo los vectores a usar para cada T
  x_T=[x3-x2;x1-x3;x2-x1];
  y_T=[y2-y3;y3-y1;y1-y2];
  %area_bis=((x2-x1)*(y3-y1)-(x3-x1)*(y2-y1))/2
  %Area de cada T
  det_T=(x_T(3)'*y_T(2)-x_T(2)'*y_T(3))/2;
  %Armo R sin burbuja
  R=(mu/(4*det_T))*(y_T*y_T'+x_T*x_T')
  
 end

trimesh(elem_vertices,vertex_coordinates(:,1),vertex_coordinates(:,2))
