# Requests tests

## ApacheBench

```shell
ab -n 5000 -c 500 http://localhost:9292/
This is ApacheBench, Version 2.3 <$Revision: 1807734 $>
Copyright 1996 Adam Twiss, Zeus Technology Ltd, http://www.zeustech.net/
Licensed to The Apache Software Foundation, http://www.apache.org/

Benchmarking localhost (be patient)
Completed 500 requests
Completed 1000 requests
Completed 1500 requests
Completed 2000 requests
Completed 2500 requests
Completed 3000 requests
Completed 3500 requests
Completed 4000 requests
Completed 4500 requests
Completed 5000 requests
Finished 5000 requests


Server Software:
Server Hostname:        localhost
Server Port:            9292

Document Path:          /
Document Length:        0 bytes

Concurrency Level:      500
Time taken for tests:   6.597 seconds
Complete requests:      5000
Failed requests:        0
Non-2xx responses:      5000
Total transferred:      420000 bytes
HTML transferred:       0 bytes
Requests per second:    757.94 [#/sec] (mean)
Time per request:       659.679 [ms] (mean)
Time per request:       1.319 [ms] (mean, across all concurrent requests)
Transfer rate:          62.18 [Kbytes/sec] received

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    1   2.1      0      10
Processing:     4  635 221.9    748     920
Waiting:        4  634 222.0    748     920
Total:         12  636 220.6    748     920

Percentage of the requests served within a certain time (ms)
  50%    748
  66%    794
  75%    802
  80%    805
  90%    815
  95%    892
  98%    900
  99%    903
 100%    920 (longest request)
 ```

### Test with a concurrency of 1000

 ```shell
 ab -n 5000 -c 1000 http://localhost:9292/
This is ApacheBench, Version 2.3 <$Revision: 1807734 $>
Copyright 1996 Adam Twiss, Zeus Technology Ltd, http://www.zeustech.net/
Licensed to The Apache Software Foundation, http://www.apache.org/

Benchmarking localhost (be patient)
Completed 500 requests
Completed 1000 requests
Completed 1500 requests
Completed 2000 requests
Completed 2500 requests
Completed 3000 requests
Completed 3500 requests
Completed 4000 requests
Completed 4500 requests
Completed 5000 requests
Finished 5000 requests


Server Software:
Server Hostname:        localhost
Server Port:            9292

Document Path:          /
Document Length:        0 bytes

Concurrency Level:      1000
Time taken for tests:   6.092 seconds
Complete requests:      5000
Failed requests:        0
Non-2xx responses:      5000
Total transferred:      420000 bytes
HTML transferred:       0 bytes
Requests per second:    820.71 [#/sec] (mean)
Time per request:       1218.458 [ms] (mean)
Time per request:       1.218 [ms] (mean, across all concurrent requests)
Transfer rate:          67.32 [Kbytes/sec] received

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    4   9.9      0      49
Processing:    24 1103 479.8   1175    1774
Waiting:       24 1103 479.9   1173    1774
Total:         54 1108 472.1   1175    1774

Percentage of the requests served within a certain time (ms)
  50%   1175
  66%   1369
  75%   1501
  80%   1563
  90%   1666
  95%   1710
  98%   1744
  99%   1754
 100%   1774 (longest request)
 ```

## Siege

```shell
siege -t 5S -c 500 http://localhost:9292/
** SIEGE 4.0.4
** Preparing 500 concurrent users for battle.
The server is now under siege...
Lifting the server siege...
Transactions:          5000 hits
Availability:        100.00 %
Elapsed time:          4.44 secs
Data transferred:         0.01 MB
Response time:          0.41 secs
Transaction rate:      1126.13 trans/sec
Throughput:          0.00 MB/sec
Concurrency:        457.56
Successful transactions:        5078
Failed transactions:            0
Longest transaction:         0.73
Shortest transaction:         0.01
```

### with concurrency of 1000

```shell
siege -t 5S -c 1000 http://localhost:9292/
** SIEGE 4.0.4
** Preparing 1000 concurrent users for battle.
The server is now under siege...
Lifting the server siege...
Transactions:          6856 hits
Availability:        100.00 %
Elapsed time:          4.77 secs
Data transferred:         0.02 MB
Response time:          0.61 secs
Transaction rate:      1437.32 trans/sec
Throughput:          0.00 MB/sec
Concurrency:        882.81
Successful transactions:        7486
Failed transactions:            0
Longest transaction:         0.94
Shortest transaction:         0.00
```
