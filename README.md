# CMP-464-Project-Code-
This is the code I made for my Data Science project.

#Roberto Martinez
#Data Science (CMP 464)
#Project: Videogame Console Sales (2008 - 2015)

import numpy as np
import matplotlib.pyplot as plt

years = [2008, 2009, 2010, 2011, 2012, 2013, 2014, 2015]
ps3 = [10.46, 13.26, 13.83, 14.42, 11.97, 8.26, 3.56, 1.34]
ps4 = [0, 0, 0, 0, 0, 4.49, 14.59, 17.37]
psp = [14.05, 9.92, 9.36, 7.38, 4.22, 2.97, 0.39, 0]
psvita = [0, 0, 0, 0.48, 3.69, 3.4, 2.3, 2.68]
xbox360 = [11.16, 10.36, 13.53, 13.95, 10.69, 6.24, 2.6, 0.93]
xbox1 = [0, 0, 0, 0, 0, 3.08, 7.91, 8.6]
wii = [24.09, 21.05, 17.26, 11.49, 5.08, 1.95, 0.52, 0.07]
wiiu = [0, 0, 0, 0, 2.17, 3.1, 3.64, 3.56]
ds = [29.47, 27.28, 20.55, 8.76, 3.01, 0.82, 0, 0]
n3ds = [0, 0, 0, 12.56, 13.48, 14.31, 9.74, 7.86]

numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21]
sales = [157.68, 154.88, 118.69, 104.25, 101.18, 85.88, 84.94, 81.51, 80.82, 61.91, 54.12, 49.1, 32.93, 29.54, 27.64, 24.65, 25.45, 10.62, 13.88, 12.39, 10.27]
consoles = ['PS2', 'DS', 'GB', 'PS1', 'Wii', 'PS3', '360', 'GBA', 'PSP', 'NES', '3DS', 'SNES', 'N64', 'SG', '2600', 'Xbox', 'PS4', 'GG', 'X1', 'Vita', 'WiiU']

plt.axis([2008, 2015, 0, 30])
line = plt.plot(years, ps3, color='black', marker='o', linestyle='solid', label='PS3')
plt.plot(years, ps4, color='blue', marker='o', linestyle='solid', label='PS4')
plt.plot(years, psp, color='gray', marker='o', linestyle='solid', label='PSP')
plt.plot(years, psvita, color='purple', marker='o', linestyle='solid', label='PS Vita')
plt.plot(years, xbox360, color='red', marker='o', linestyle='solid', label='Xbox 360')
plt.plot(years, xbox1, color='green', marker='o', linestyle='solid', label='Xbox One')
plt.plot(years, wii, color='yellow', marker='o', linestyle='solid', label='Wii')
plt.plot(years, wiiu, color='pink', marker='o', linestyle='solid', label='Wii U')
plt.plot(years, ds, color='brown', marker='o', linestyle='solid', label='DS')
plt.plot(years, n3ds, color='orange', marker='o', linestyle='solid', label='3DS')
plt.title("Videogame Console Sales (2008-2015)")
plt.xlabel("Years")
plt.ylabel("Unit Sales (in millions)")
plt.legend()
plt.show()

#ind = np.arange(years)
width = 0.50

fig, ax = plt.subplots()
bar1 = ax.bar(years, ds, width, color='brown', label='DS')
bar2 = ax.bar(years, n3ds, width, color='orange', label='3DS')
bar3 = ax.bar(years, wiiu, width, color='pink', label='Wii U')
bar4 = ax.bar(years, wii, width, color='yellow', label='Wii')
bar5 = ax.bar(years, xbox1, width, color='green', label='Xbox One')
bar6 = ax.bar(years, xbox360, width, color='red', label='Xbox 360')
bar7 = ax.bar(years, psvita, width, color='silver', label='PS Vita')
bar8 = ax.bar(years, psp, width, color='gray', label='PSP')
bar9 = ax.bar(years, ps4, width, color='blue', label='PS4')
bar10 = ax.bar(years, ps3, width, color='silver', label='PS3')

ax.legend()

def label(bars):
    for bar in bars:
        height = bar.get_height()
        ax.text(bar.get_x() + bar.get_width()/2., 1.05*height, '%d' % int(height), ha='center', va='bottom')

label(bar1)
label(bar2)
label(bar3)
label(bar4)
label(bar5)
label(bar6)
label(bar7)
label(bar8)
label(bar9)
label(bar10)

plt.title("Videogame Console Sales (2008-2015)")
plt.xlabel("Years")
plt.ylabel("Unit Sales (in millions)")
plt.show()

xs = [i + 0.1 for i, _ in enumerate(consoles)]

plt.bar(xs, sales)

plt.ylabel("Unit Sales (in millions)")
plt.xlabel("Videogame Consoles")
plt.title("Videogame Console Sales as of October 2015")
plt.xticks([i + 0.5 for i, _ in enumerate(consoles)], consoles)
plt.show()

plt.scatter(numbers, sales)

for console, count, sale in zip(consoles, numbers, sales):
    plt.annotate(console,
        xy=(count, sale),
        xytext=(5, -5),
        textcoords='offset points')

plt.title("Videogame Console Sales as of October 2015")
plt.ylabel("Unit Sales (in millions)")
plt.show()
