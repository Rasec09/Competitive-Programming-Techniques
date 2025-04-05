### Range Sum Query 1D array - Range Update O(1) / Point Query O(n)
```
void update(int l, int r, int x) {
	a[l] += x;
	a[r + 1]--;
}

int query(int idx) {
	vector<int> prefix(n);
	for (int i = 0; i < n; i++) {
		prefix[i] = a[i];
		if (i)
			prefix[i] += prefix[i - 1];
	}
	return prefix[idx];
}
```
