# SimFin Tutorials

[Original repository on GitHub](https://github.com/simfin/simfin-tutorials)


## Introduction

[SimFin](https://github.com/simfin/simfin) is a database with financial
data such as Income Statements, Balance Sheets and Cash Flow Statements,
along with a simple Python API for downloading and using the data. These
tutorials show how to use the SimFin API and data.


## Videos

There is a [video](https://www.youtube.com/watch?v=nCY8a0KeeAE)
on YouTube with an overview of these tutorials,
and [another video](https://www.youtube.com/watch?v=zstXCc8iV2U)
on how to backtest and optimize a stock-screener based on Tutorial 7.


## Tutorials

1. Basics ([Notebook](https://github.com/simfin/simfin-tutorials/blob/master/01_Basics.ipynb)) ([Google Colab](https://colab.research.google.com/github/simfin/simfin-tutorials/blob/master/01_Basics.ipynb))
2. Resampling ([Notebook](https://github.com/simfin/simfin-tutorials/blob/master/02_Resampling.ipynb)) ([Google Colab](https://colab.research.google.com/github/simfin/simfin-tutorials/blob/master/02_Resampling.ipynb))
3. Growth & Returns ([Notebook](https://github.com/simfin/simfin-tutorials/blob/master/03_Growth_Returns.ipynb)) ([Google Colab](https://colab.research.google.com/github/simfin/simfin-tutorials/blob/master/03_Growth_Returns.ipynb))
4. Signals ([Notebook](https://github.com/simfin/simfin-tutorials/blob/master/04_Signals.ipynb)) ([Google Colab](https://colab.research.google.com/github/simfin/simfin-tutorials/blob/master/04_Signals.ipynb))
5. Data Hubs ([Notebook](https://github.com/simfin/simfin-tutorials/blob/master/05_Data_Hubs.ipynb)) ([Google Colab](https://colab.research.google.com/github/simfin/simfin-tutorials/blob/master/05_Data_Hubs.ipynb))
6. Performance Tips ([Notebook](https://github.com/simfin/simfin-tutorials/blob/master/06_Performance_Tips.ipynb)) ([Google Colab](https://colab.research.google.com/github/simfin/simfin-tutorials/blob/master/06_Performance_Tips.ipynb))
7. Stock Screener ([Notebook](https://github.com/simfin/simfin-tutorials/blob/master/07_Stock_Screener.ipynb)) ([Google Colab](https://colab.research.google.com/github/simfin/simfin-tutorials/blob/master/07_Stock_Screener.ipynb))
8. Statistical Analysis ([Notebook](https://github.com/simfin/simfin-tutorials/blob/master/08_Statistical_Analysis.ipynb)) ([Google Colab](https://colab.research.google.com/github/simfin/simfin-tutorials/blob/master/08_Statistical_Analysis.ipynb))
9. Machine Learning ([Notebook](https://github.com/simfin/simfin-tutorials/blob/master/09_Machine_Learning.ipynb)) ([Google Colab](https://colab.research.google.com/github/simfin/simfin-tutorials/blob/master/09_Machine_Learning.ipynb))
10. Neural Networks ([Notebook](https://github.com/simfin/simfin-tutorials/blob/master/10_Neural_Networks.ipynb)) ([Google Colab](https://colab.research.google.com/github/simfin/simfin-tutorials/blob/master/10_Neural_Networks.ipynb))

There is also a collection of small recipes ([Notebook](https://github.com/simfin/simfin-tutorials/blob/master/Small_Recipes.ipynb)) ([Google Colab](https://colab.research.google.com/github/simfin/simfin-tutorials/blob/master/Small_Recipes.ipynb))


## Downloading

If you want to run these tutorials on your own computer, then it is
recommended that you download the whole repository from GitHub,
instead of just downloading the individual Python Notebooks.


### Git

The easiest way to download and install this is by using git from the command-line:

    git clone https://github.com/simfin/simfin-tutorials.git

This creates the directory `simfin-tutorials` and downloads all the files to it.

This also makes it easy to update the files, simply by executing this
command inside that directory:

    git pull


### Zip-File

You can also [download](https://github.com/simfin/simfin-tutorials/archive/master.zip)
the contents of the GitHub repository as a Zip-file and extract it manually.


## Installation

If you want to run these tutorials on your own computer, then it is best
to use a virtual environment when installing the required packages,
so you can easily delete the environment again. You write the following
in a Linux terminal:

    virtualenv simfin-env

Or you can use [Anaconda](https://www.anaconda.com/download) instead of a virtualenv:

    conda create --name simfin-env python=3

Then you switch to the virtual environment and install the required packages.

    source activate simfin-env
    pip install -r requirements.txt

When you are done working on the project you can deactivate the virtualenv:

    source deactivate


## How To Run

Once you have installed the required Python packages in a virtual environment,
you run the following command from the `simfin-tutorials` directory to view
and edit the Notebooks:

    source activate simfin-env
    jupyter notebook


### Run in Google Colab

If you do not want to install anything on your own computer, then the Notebooks
can be viewed, edited and run entirely on the internet by using
[Google Colab](https://colab.research.google.com).

You can click the "Google Colab"-link next to the tutorials listed above.
You can view the Notebook on Colab but in order to run it you need to login using
your Google account.

All the required Python packages should already be installed on Google Colab,
except for simfin which you can install by executing the following command
at the top of the Notebook:

    !pip install simfin

If that is insufficient, then you can clone this entire GitHub repository
to your Google Colab account, and execute the following commands at the
top of the Notebook, to install all requirements:

    # Clone the repository from GitHub to Google Colab's temporary drive.
    import os
    work_dir = "/content/simfin-tutorials/"
    if not os.path.exists(work_dir):
        !git clone https://github.com/simfin/simfin-tutorials.git
    os.chdir(work_dir)
    
    # Install the required Python packages.
    !pip install -r requirements.txt

Note that you will need to run this every time you login to Google Colab.

## Testing

All the Notebooks can be run automatically and tested for errors. This is
particularly useful for developers who are making changes to the simfin
package, because it complements the unit-tests and data-tests with more
realistic use-cases.

First you need to install [nbval](https://pypi.org/project/nbval/):

    pip install nbval

Then you can execute all the Notebooks and test them for errors by running
the following command from the directory where the Notebooks are located:
 
    pytest --nbval-lax -v

Note that this will only test for errors and exceptions. It will not test
whether the new output matches the old output found in the Notebooks,
because the datasets are continually updated.


## License (MIT)

This is published under the
[MIT License](https://github.com/simfin/simfin-tutorials/blob/master/LICENSE.txt)
which allows very broad use for both academic and commercial purposes.

You are very welcome to modify and use this source-code in your own project.
Please keep a link to the [original repository](https://github.com/simfin/simfin-tutorials).
