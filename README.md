Package to download historical data from Darwinex with different data format.

Darwinex data download is performed via FTP, in each file that you can downloade there is informatio of each operation performed in the ticker. This package allows you to download the data in ohlc format ready for analysis with python with different periodicity.

## Table of Contents


  * [Requirements](#Requirements)
  * [Installation](#Installation)
  * [Documentation and Tutorials](#Documentation-and-Tutorials)
  * [Questions, Suggestions and Bugs](#questions--suggestions-and-bugs)
  * [Contributing / Development](#contributing--development)
  * [License](#license)



## Requirements

The following are required before installing cooltools:

* Python 3.7+
* `numpy`

## Installation

```sh
pip install DarwinexDownloader
```

or you can install the latest version directly from github:

```sh
    $ pip install https://github.com/igarciaferreira/DarwinexDownloader/archive/refs/heads/main.zip
``` 

## Documentation and Tutorials

Once you have installed the library you have to import it in the source code:

```python
import darwinexDownloader
```

This the library in your code, you can use darwinexDownloader to connect with Darwinex:

```python
dwnx = darwinexDownloader.Connection('your_user', 'your_password') # clase
```

At this time, we are ready to download the data:

```python
data = dwnx.download('EURUSD', "28-06-2022", "29-06-2022", '15Min')
```

Now in the 'data' variable we have the ohlc data ready to make our analysis.

| Date | open    | high    | low     | close   | volume      |
| :--                 | |:---: | :---:  |:---:   | :---:  |        ---: | 
| 2022-06-28 00:00:00 | 1.05797 | 1.05850 | 1.05789 | 1.05810 | 952330000.0 |
| 2022-06-28 00:15:00 | 1.05812 | 1.05852 | 1.05807 | 1.05825 | 549950000.0 |
| 2022-06-28 00:30:00 | 1.05824 | 1.05853 | 1.05773 | 1.05779 | 503900000.0 |
|         ...         |   ...   |   ...   |   ...   |   ...   |     ...     |
| 2022-06-29 23:30:00 | 1.05218 | 1.05238 | 1.05204 | 1.05237 | 244950000.0 |
| 2022-06-29 23:45:00 | 1.05236 | 1.05238 | 1.05217 | 1.05220 | 291050000.0 |

For the moment, date format must always be as follows: "dd-mm-yyyy" where the first date is the start date and the second is the end date.

The frecuency has the format used by [pandas timeframes](https://pandas.pydata.org/pandas-docs/stable/user_guide/timeseries.html#offset-aliases) where the most used in trading can be:
* '1Min' 
* '5Min'
* '15Min'
* '30Min'
* '1H'
* '4H'
* '1D'
* 'Week'
* 'Month'

## Questions, Suggestions and Bugs

Feel free to open an issue [here](https://github.com/igarciaferreira/DarwinexDownloader/issues). 

## Contributing / Development

Contributions welcome. 

## License

[MIT License](./LICENSE.txt). Iván García-Ferreira