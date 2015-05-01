# genderator

[![Build Status](https://img.shields.io/travis/davidmogar/genderator.svg)](https://travis-ci.org/davidmogar/genderator)
[![PyPi](https://img.shields.io/pypi/v/genderator.svg)](https://pypi.python.org/pypi/genderator)
[![License](https://img.shields.io/github/license/davidmogar/genderator.svg)](https://github.com/davidmogar/genderator/blob/master/LICENSE)

Genderator is a Python library to process spanish names to guess their
gender.

For this to work, the libray uses the next datasets from [Instituto
Nacional de Estadística](http://www.ine.es):

-  **name\_surname\_ratio**: List of words that could be both, a name or
   a surname, and shows the probability to be a surname.
-  **names\_ine**: List of registered names on Spain, with the
   probability for each one to be a male or a female name.
-  **surnames\_ine**: List of registeres surnames on Spain.

## Installation

The easiest way to install the latest version is by using pip to pull it
from [PyPI](https://pypi.python.org/pypi/genderator):

```
pip install genderator
```

You may also use Git to clone the repository from Github and install it
manually:

```
git clone https://github.com/davidmogar/genderator.git
cd genderator
python setup.py install
```

## Usage

The next code shows a sample usage of this library:

``` python
import genderator

guesser = genderator.Parser()
answer = guesser.guess_gender('David Moreno García')
if answer:
    print(answer)
else:
    print('Name doesn\'t match')
```

Output:

```
OrderedDict([('names', ['david']), ('surnames', ['moreno', 'garcia']), ('real_name', 'david'), ('gender', 'Male'), ('confidence', 1.0)])
```