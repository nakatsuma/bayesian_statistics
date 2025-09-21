# BAYESIAN STATISTICS A/B <!-- omit in toc -->

## Course materials for BAYESIAN STATISTICS A/B  <!-- omit in toc -->

Teruo Nakatsuma (Faculty of Economics, Keio University, Japan)

---

- [How to set up Python and necessary packages](#how-to-set-up-python-and-necessary-packages)
  - [Step 1: Installing Anaconda](#step-1-installing-anaconda)
  - [Step 2: Creating an environment](#step-2-creating-an-environment)
  - [Troubleshooting about installation](#troubleshooting-about-installation)
    - [1. Retry installation](#1-retry-installation)
    - [2. (macOS) Installing Command Line Tools for Xcode](#2-macos-installing-command-line-tools-for-xcode)
- [How to start JupyterLab](#how-to-start-jupyterlab)
  - [Method 1: From the command line](#method-1-from-the-command-line)
  - [Method 2: From Anaconda Navigator](#method-2-from-anaconda-navigator)
- [Jupyter Notebooks and related files in `notebook-a`](#jupyter-notebooks-and-related-files-in-notebook-a)

---

## How to set up Python and necessary packages

I strongly recommend using [Anaconda](https://www.anaconda.com/). It can install Python along with numerous essential packages at once and allows us to manage those packages flexibly.

### Step 1: Installing Anaconda

1. If you have an older Anaconda on your PC, uninstall it completely by folloiwng [instructions](https://docs.anaconda.com/anaconda/install/uninstall/).

2. Download an Anaconda installer (Windows, macOS or Linux) from [here](https://www.anaconda.com/products/distribution). Choose an installer for your OS. For macOS, you should check whether Intel chip or Apple Silicon chip is used and download the corresponding installer.

3. Doubleclick the installer and follow the instructions on the screen. Do not change the default settings.

### Step 2: Creating an environment

Start `Anaconda Powershell Prompt` (Windows) or `Terminal` (macOS, Linux) and type

```IPython
conda update conda
```

This will update conda (package manager) in Anaconda.

(Optional) To update all packages, type

```IPython
conda update -n base --all
```

Then type

(Windows)

```IPython
conda create -n bayes -c conda-forge jupyterlab ipywidgets seaborn pymc python-graphviz
```

(macOS)

```IPython
conda create -n bayes -c conda-forge jupyterlab ipywidgets seaborn pymc numpyro python-graphviz
```

This will create the environment for PyMC. Then type

```IPython
conda activate bayes
```

(Windows) Install `numpyro` by typing

```IPython
pip install numpyro
```

Finally, type

```IPython
python -m ipykernel install --user --name bayes --display-name "Python (Bayes)"
```

Now you are ready for Python!

---

## Troubleshooting about installation

### 1. Retry installation

If you encounter any errors during the installation process, go back to the default environment by typing

```IPython
conda deactivate
```

and remove `bayes` by typing

```IPython
conda env remove -n bayes
```

Then redo **Step 2**.

### 2. (macOS) Installing Command Line Tools for Xcode

In case the computer says `Command Line Tools for Xcode` is missing,  install it as follows.

1. Install `Xcode` from App Store.

2. Start `Xcode`. If a pop-up window asks you to install additional tools, follow the instruction. Quit `Xcode`.

3. Start `Terminal` and install `Command Line Tools for Xcode` by typing

``` IPython
sudo xcode-select --install
```

If asked, type your login password.

---

## How to start JupyterLab

### Method 1: From the command line

Start `Anaconda Powershell Prompt` (Windows) or `Terminal` (macOS, Linux) and type

```IPython
jupyter lab
```

Your default browser will pop up.

### Method 2: From Anaconda Navigator

(Windows) From the `Start Menu`, search for `Anaconda Navigator` and click to open it

(macOS) Open `Launchpad` and click the `Anaconda-Navigator` icon.

Then click the icon named `JupyterLab`.

## Jupyter Notebooks and related files in `notebook`

| file name                  | description                             |
|:---------------------------|:----------------------------------------|
| ar1_process.ipynb          | convergence of the AR(1) process        |
| bayes_bernoulli.ipynb      | Bayesian inference on Bernoulli dist.   |
| bayes_exponential.ipynb    | Bayesian inference on exponential dist. |
| bayes_normal.ipynb         | Bayesian inference on normal dist.      |
| bayes_poisson.ipynb        | Bayesian inference on Poisson dist.     |
| HMDA.csv                   | Home Mortgage Disclosure Act data       |
| housing_price.ipynb        | hedonic price model of houses           |
| Housing.csv                | sales prices of houses                  |
| mortgage_denial.ipynb      | logit / probit model of mortgage denial |
| prussian.csv               | Prussian army horse kick data           |
| simple_regression.ipynb    | simple regression model                 |
| speedlimit.ipynb           | effect of speed limits on accidents     |
| StrikeDur.csv              | strikes duration data                   |
| strikes_duration.ipynb.    | exponential model of strikes duration   |
| Traffic.csv                | speed limit and traffic accident data   |
| USStocksSW.csv             | monthly US stock returns data           |

---