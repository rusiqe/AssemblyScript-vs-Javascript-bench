#Benchmark List

##List (Progress: 7/12)
|ID | Benchmark | Status | Test |
|--------|--------|--------|--------|
|1 | back-prop  |  done  | The random value of `hidden_weights` is incorrect |
|2 | bfs | working | |
|3 | crc | | |
|4 | fft | done | About 112 seconds when n = 10 |
|5 | hmm | done | Tested |
|6 | lavamd |   | |
|7 | lud | done | Get different but correct result from MATLAB `lu` function |
|8 | nqueens| | |
|9 | nw | | |
|10| page-rank | done | Read data file `pagerank.data` |
|11| spmv | done | `spmv_ostrich_loop` (0.168) is faster than `spmv_ostrich` (3.067) |
|12| srad | done | precision problem in the expected result (expected output of 52608 but received 5.285761e+04 instead) |

###Updated
* Lud has three data files for value checking: row indices, column indices and expected value files.
* Page-rank has `pagerank.data` for data input (in the same directory, the same as Lud benchmark).
* Srad is feeded with a fixed size image matrix, `../data/image.pgm`. **NO random number** in this benchmark

###Random number
```matlab
% set rand seed
s = RandStream('mcg16807','Seed',49734321);
RandStream.setDefaultStream(s);
```


###Output
```matlab
msg = sprintf('{ \"status\": %d, \"options\": \"%d\", \"time\": %f seconds}\n', 1, two_exp, elapsedTime);
disp(msg);
```

### Problems
In page-rank: the precision of double is maximum 16-digits after dot.