# Визуализация данных - Matplotlib и Seaborn

## Styling

### Title, labels, text, subplots

    :::python
    plt.title('Title')
    plt.title('Part1\nPart2', fontsize=16)
    plt.xlabel('Xlabel', fontsize=10)  # fontsize is opt

    plt.yscale('log')
    plt.grid(True)

    plt.xticks(np.arange(min(x), max(x)+1, 1.0))

    plt.gca().set_ylim([0, 2000])

    plt.subplot(211)
    plt.plot(x1, y1)
    plt.subplot(212)
    plt.plot(x2, y2)

    plt.text(60, .025, r'$\mu=100,\ \sigma=15$')

### Colors

    :::python
    b: blue
    g: green
    r: red
    c: cyan
    m: magenta
    y: yellow
    k: black
    w: white

### Linestyles

    :::python
    '-'
    '--'
    '-.'
    ':'

### Basic Seaborn Themes

    :::python
    darkgrid
    whitegrid
    dark
    white
    ticks

    sns.set_style("whitegrid")

### Figure Size

    :::python
    from pylab import rcParams
    rcParams['figure.figsize'] = 10, 5 

    plt.plot(x, y, figsize=(10,10))

Also Seaborn does pictures looks better


## Plots

### Common Plot

    :::python
    plt.plot(x, y, 'r--')

### Histogram/Distribution Plot

    :::python
    sns.distplot(x, kde=False, rug=False);

### Errorbars

    :::python
    plt.errorbar(x, y, xerr=xerr, yerr=yerr, fmt='o')

### Scatter Plots    

    :::python
    plt.scatter(x, y, color='r', s=2*s, marker='^', alpha=.4)
    # s - size
    # alpha - blending

    sns.jointplot(x="x", y="y", data=df);


### Bubble Plot

http://matplotlib.org/examples/shapes_and_collections/scatter_demo.html

### Strip Plot

    :::python
    sns.stripplot(x="day", y="total_bill", data=tips, jitter=False);

### Box Plot

    :::python
    sns.boxplot(x="day", y="total_bill", hue="time", data=tips);

### Bar Plot

    :::python
    index = np.arange(len(labels))
    plt.bar(index, values)
    plt.barh(index, values)  # horizontal
    plt.xticks(index, labels)

For multiple variables see examples

* [Example 1](https://pythonspot.com/en/matplotlib-bar-chart/)
* [Example 2](http://matplotlib.org/examples/pylab_examples/barchart_demo.html)

Seaborn plots for datasets

    :::python
    sns.barplot(x="sex", y="survived", hue="class", data=titanic);  # Average
    sns.countplot(x="deck", data=titanic, palette="Greens_d");  # Count
    sns.countplot(y="deck", data=titanic, palette="Greens_d");  # Count - horizontal

### Color Plot

http://matplotlib.org/examples/pylab_examples/pcolor_demo.html

## Another approach to Matplotlib (fig, ax)

    # Create a figure instance
    fig = plt.figure(1, figsize=(9, 6))

    # Create an axes instance
    ax = fig.add_subplot(111)

    # Create the boxplot
    bp = ax.boxplot(data_to_plot)

    # Save the figure
    fig.savefig('fig1.png', bbox_inches='tight')

## Examples

* [Seaborn - linear regression](https://stanford.edu/~mwaskom/software/seaborn/tutorial/regression.html)
* [Seaborn Examples](https://stanford.edu/~mwaskom/software/seaborn/examples/index.html)
* [Errorbars](http://matplotlib.org/1.2.1/examples/pylab_examples/errorbar_demo.html)

