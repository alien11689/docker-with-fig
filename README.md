I expect that you have installed docker (https://www.docker.com/) and fig (http://www.fig.sh/) on your machine.

Build all containers:

$ fig build



Or only selected containers:

$ fig build scala groovy



Run container:

$ fig run CONAINER\_NAME



Run command on continer

$ fig run CONAINER\_NAME COMMAND



Available containers:

- haskell

- scala

- groovy

- python27

- python34

- clojure
