# Run the script

```bash
$ sh runtest.sh
```

# Examine the data

Assuming you have the awesome [csvkit](http://csvkit.readthedocs.io/en/1.0.1/index.html) then it is fairly easy to get a quick view of what you did in your runs. If not the get it with the following line of command (more info [here](http://csvkit.readthedocs.io/en/749/tricks.html#installation)).

```bash
$ sudo pip install csvkit
```
Now, let's work through our small dataset.

```bash
$ cd Output/
$ csvlook results_20170208_1016.csv
|---------------------+----------------------|
|  column1            | column2              |
|---------------------+----------------------|
|  5381.607000000031  |  9135.547000000088   |
|  4831.132000000025  |  5121.834000000035   |
|  4966.146999999864  |  5350.357000000031   |
|  5008.573999999953  |                      |
|  3650.9819999998854 |  4306.622999999945   |
|  9516.393000000335  |  4011.6949999996905  |
|  7733.321999999589  |  4022.1440000000257  |
|  4230.80600000003   |  4934.671999999864   |
|  4849.1039999998975 |  5296.432000000095   |
|  4918.529999999919  |  7818.144000000302   |
|  3894.4950000000063 |  5405.8500000001     |
|  .................  |  .................   |
|  4730.179000000135  |  4530.756999999994   |
|  12699.122999999872 |  7610.573999999815   |
|  4435.840999999982  |  8118.466999999782   |
|  3989.4020000001547 |  4721.0369999997965  |
|  7853.458000000046  |  4258.878000000095   |
|  7708.621000000221  |  9581.052            |
|  4230.597000000216  |  9050.584999999955   |
|                     |  4451.7470000000685  |
|  3939.024999999674  |  5741.194000000178   |
|  4738.648000000012  |                      |
|  5154.950000000099  |  4647.0140000001265  |
|                     |  7852.577999999994   |
|  6527.384999999867  |  7495.597999999973   |
|  3799.1010000000642 |                      |
|---------------------+----------------------|
```
# Descriptive statistics
Now, take a look on the basic figures for our two pages.

```bash
$ csvstat results_20170208_1016.csv -H
  1. column1
        <class 'float'>
        Nulls: True
        Min: 3592.728000000079
        Max: 21223.57000000011
        Sum: 633312.8869999982
        Mean: 7036.809855555536
        Median: 4942.338499999892
        Standard Deviation: 4454.970173002213
        Unique values: 90
  2. column2
        <class 'float'>
        Nulls: True
        Min: 3744.9320000000625
        Max: 26533.20499999995
        Sum: 585734.0939999999
        Mean: 6810.861558139534
        Median: 5176.866000000132
        Standard Deviation: 4288.08854581262
        Unique values: 86

Row count: 100
```
# Schedule the script

```bash
$ at now +24 hours -f runtest.sh
```
