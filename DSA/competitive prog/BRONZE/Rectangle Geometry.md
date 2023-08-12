### Finding area
`length`: vertical
`width`: horizontal

1. width = tr_x - bl_x
2. length = tr_y - bl_y
3. area = width * length*

```cpp
long long area(int bl_x, int bl_y, int tr_x, int tr_y) {
	long long length = tr_y - bl_y;
	long long width = tr_x - bl_x;	
	return length * width;
}
```

### Checking if two rectangles interesct
there only two cases where they do not interect
1. $tr_{a_{y}} <= bl_{b_{y}}$  or  $bl_{a_{y}}>= tr_{b_y}$
2. $bl_{a_{x}}>= tr_{b_{x}}$ or  $tr_{a_{X}} <= bl_{b_x}$

```cpp
bool intersect(vector<int> s1, vector<int> s2) {
	int bl_a_x = s1[0], bl_a_y = s1[1], tr_a_x = s1[2], tr_a_y = s1[3];
	int bl_b_x = s1[0], bl_b_y = s1[1], tr_b_x = s1[2], tr_b_y = s1[3];

	// no overlap
	if (bl_a_x >= tr_b_x || tr_a_x <= bl_b_x || bl_a_y >= tr_b_y || tr_a_y < bl_b_y) {
	return false;
	} else {
		return true;
	}
}
```

### Finding area of intersection
- find rectangle's L, W that intersected
- `width = min(tr_a_x, tr_b_x) - max(bl_a_x, bl_b_x)`
- `height = min(tr_a_y, tr_b_y) - max(bl_a_y, bl_b_y)`

```cpp
int inter_area(vector<int> s1, vector<int> s2) {
	int bl_a_x = s1[0], bl_a_y = s1[1], tr_a_x = s1[2], tr_a_y = s1[3];
	int bl_b_x = s2[0], bl_b_y = s2[1], tr_b_x = s2[2], tr_b_y = s2[3];

	return ((min(tr_a_x, tr_b_x) - max(bl_a_x, bl_b_x)) *
	        (min(tr_a_y, tr_b_y) - max(bl_a_y, bl_b_y)));
}
```

