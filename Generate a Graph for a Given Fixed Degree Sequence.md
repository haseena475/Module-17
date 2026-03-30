# Ex. No: 17A - Generate a Graph for a Given Fixed Degree Sequence

## AIM:
To write a Python program to generate a graph for a given **fixed degree sequence**.

## ALGORITHM:

**Step 1**: Start the program.

**Step 2**: Check if the sum of the degree sequence is even.  
> (A necessary condition for the sequence to be graphical.)

- If not even, print an error message and exit the program.

**Step 3**: Use the **Havel-Hakimi algorithm** to determine whether a simple graph can be constructed from the sequence, and to generate the graph.

**Step 4**: If the graph is successfully created, **visualize it** using a graph drawing function (e.g., `networkx.draw()`).

**Step 5**: End the program.

## PYTHON PROGRAM

```
def printMat(degseq, n):
	
	# n is number of vertices
	mat = [[0] * n for i in range(n)]

	for i in range(n):
		for j in range(i + 1, n):

			# For each pair of vertex decrement
			# the degree of both vertex.
			if (degseq[i] >0 and degseq[j] > 0):
				degseq[i] -= 1
				degseq[j] -= 1
				mat[i][j] = 1
				mat[j][i] = 1

	# Print the result in specified form
	print("      ", end ="")
	for i in range(n):
		print(" ", "(", i, ")", end ="")
	print()
	print()
	for i in range(n):
		print("  ", "(", i, ")", end = " ")
		for  j in range(n):
			print("  ", mat[i][j], end = " ")
		print()

# Driver Code
degseq=[]
for i in range(0, 5):
    ele = int(input())
  
    degseq.append(ele)
#degseq =[v0,v1,v2,v3,v4]

n = len(degseq)
printMat(degseq, n)
```

## OUTPUT
<img width="1011" height="285" alt="image" src="https://github.com/user-attachments/assets/35bbd1b7-f68c-405c-9ec9-abf4c78a67ef" />


## RESULT

Thus the python program was initialised and executed successfully.
