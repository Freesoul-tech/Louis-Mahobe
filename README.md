from typing import ValuesView


initial_thickness = 0.00008 # mm

# Number of folds
folds = 4
final_thickness = initial_thickness * (2 ** folds)
initial_thickness = 0.00008 # mm

# Number of folds
folds = 43

final_thickness = initial_thickness * (2 ** folds)

# Print the result
print(f"The thickness of the paper after folding it {folds} times is {final_thickness} mm.")
print(f"thickness:{final_thickness/10000:.2f}, kilometres")

import time

start = time.time()
elapsed_time = time.time() - start
print("time : {}[s]".format(elapsed_time))
print(f"Time:{elapsed_time/60:.2f},minutes")


import matplotlib.pyplot as plt
%matplotlib inline
x_values = range(folds + 1)  # Fold numbers from 0 to folds
y_values = [initial_thickness * (2 ** i) for i in x_values]

plt.title("thickness of folded paper")
plt.xlabel("number of folds")
plt.ylabel("thickness [m]")
plt.plot(x_values, y_values)
plt.show()

plt.title("thickness of folded paper")
plt.xlabel("number of folds")
plt.ylabel("thickness[m]")
plt.tick_params(labelsize=20)
plt.plot(x_values, [i/1000 for i in y_values])
plt.plot(x_values, y_values, 'go--', linewidth=2, markersize=12)
plt.plot(x_values, y_values, color='green', marker='o', linestyle='dashed',
     linewidth=2, markersize=12)
plt.show()


