```python
with open(self.DATA_FILE) as f:
	reader = csv.reader(f)
	dataset = [row for row in reader]
	self.__dataset = dataset[1:]
```

