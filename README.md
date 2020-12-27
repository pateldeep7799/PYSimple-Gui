# PYSimple-Gui


Data science GUI programs with awesome `PySimpleGUI` package.

---

## What is `PySimpleGUI` and what is this repo?

As per their website, ___"Python GUI For Humans - Transforms tkinter, Qt, Remi, WxPython into portable people-friendly Pythonic interfaces"___. In this repo, I specifically focus on creating simple demo programs related to data science (simple analytics, statistical modeling and visualizations, basic machine learning) using this powerful GUI building tool.

## Requirements

Install `PySimpleGUI` by,
```
pip install pysimplegui
```

You will also need,

- Numpy
- Pandas
- Matplotlib
- Scikit-learn
- Seaborn

etc. to run the demo codes.

## A very simple [random integer generator app](https://github.com/pateldeep7799/PYSimple-Gui/blob/main/GenRandom.py)

Here is the code to program this app,

```
import PySimpleGUI as sg
import numpy as np

# Update function
def update():
    r = np.random.randint(1,100)
    text_elem = window['-text-']
    text_elem.update("This is a random integer: {}".format(r))

# Define the window's contents i.e. layout
layout = [[sg.Button('Generate',enable_events=True, key='-FUNCTION-', font='Helvetica 16')],
         [sg.Text('This is a random integer:', size=(25, 1), key='-text-', font='Helvetica 16')]]

# Create the window
window = sg.Window('Generate random integer', layout, size=(350,100))

# Event loop
while True:
    event, values = window.read()
    if event in (sg.WIN_CLOSED, 'Exit'):
        break
    if event == '-FUNCTION-':
        update()

# Close the window i.e. release resource
window.close()
```

When you save this code in a Python script and run it, you will see a simple window pop up where you can click on a button to call the `update` function as many times as you want (note the `while True` loop in the code for this infinite loop action) and generate a random integer between 1 and 99.

![genrandom](https://raw.githubusercontent.com/pateldeep7799/PYSimple-Gui/main/images/GenRandom.gif)

Although this is a very simple code, it features,

- layout (with styling arguments e.g. `size` and `font`) and a window
- a button element which calls an external function (event)
- the function updating a text element of the window object

We can essentially follow the same path and add more layers of layout, events, logic, and widgets to make powerful data science apps.

---

## [App to show other widgets](https://github.com/pateldeep7799/PYSimple-Gui/blob/main/FontUpdate.py) (`FontUpdate.py`)

Just run with `python FontUpdate.py` command and you will see this window pop up where you can dynamically update the font of the text. Here is the demo video,

![fontupdate](https://raw.githubusercontent.com/pateldeep7799/PYSimple-Gui/main/images/FontUpdate.gif)

This app gets you familiar with other widgets available,

- slider
- checkboxes

---

## Demo of `SimpleDataFrame.py` ([Pandas DataFrame app](https://github.com/pateldeep7799/PYSimple-Gui/blob/main/SimpleDataFrame.py))

There are both Jupyter notebooks and .PY scripts. The simplest way to run a GUI is to execute the .PY scripts, e.g.
```
python SimpleDataFrame.py
```

### Input file
At the start, it will ask you for a dataset file (a CSV)

![input](https://raw.githubusercontent.com/pateldeep7799/PYSimple-Gui/main/images/SimpleDataFrame-0.PNG)

### File browser
When you click on the 'Browse' button, it will show a file browser dialog first. Make sure you select the correct dataset for this demo from under the `data` directory.

![browser](https://raw.githubusercontent.com/pateldeep7799/PYSimple-Gui/main/images/SimpleDataFrame-1.PNG)

### Prompts
After you select the `cars.csv`, you will see other prompts popping up,

![prompts](https://raw.githubusercontent.com/pateldeep7799/PYSimple-Gui/main/images/SimpleDataFrame-6.png)
### Dataset
If you click 'Yes' on that last prompt, you will see the dataset that was read in a new window,

![data](https://raw.githubusercontent.com/pateldeep7799/PYSimple-Gui/main/images/SimpleDataFrame-5.PNG)
### Descriptive stats
After you close that window, a new popup will ask if you want to see the descriptive statistics about this dataset. If you click 'Yes', then you will see something like this,

![stat](https://raw.githubusercontent.com/pateldeep7799/PYSimple-Gui/main/images/SimpleDataFrame-7.PNG)
### A plot
After you close that window, another popup will ask if you want to see a sample plot. If you click 'Yes', then you will see something like this,

![plot](https://raw.githubusercontent.com/pateldeep7799/PYSimple-Gui/main/images/SimpleDataFrame-8.PNG)
### Play with the notebooks if you like
If you want to experiment with the code, you can look at the Notebooks and play with them.

---

## [Random scatter plots](https://github.com/pateldeep7799/PYSimple-Gui/blob/main/DrawRandom.py)

Generate as many random scatter plots as you wish.

![drawrandom](https://raw.githubusercontent.com/pateldeep7799/PYSimple-Gui/main/images/DrawRandom.gif)

---

## [Polynomial fitting](https://github.com/pateldeep7799/PYSimple-Gui/blob/main/PolyFit.py)

A simple 2nd degree polynomial fitting app wher you can adjust the noise level of the randomly generated data.

![polyfit](https://raw.githubusercontent.com/pateldeep7799/PYSimple-Gui/main/images/PolyFitting.gif)

---

## [A Scikit-learn model fitting example](https://github.com/pateldeep7799/PYSimple-Gui/blob/main/PimaPrediction.py)

We build a simple app which lets you load the [Pima Indians diabetes](https://www.kaggle.com/uciml/pima-indians-diabetes-database) dataset and fit a Random Forest model to this data using Scikit-learn in the background.

![pima](https://raw.githubusercontent.com/pateldeep7799/PYSimple-Gui/main/images/Pima-Prediction.gif)

---






