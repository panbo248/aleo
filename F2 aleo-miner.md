#  aleo-miner

### 版本号

2.8.8
- Solved the problem of abnormal exit of mining process under high difficulty.

### start

```
chmod +x aleo.sh && chmod +x aleo-miner
./aleo.sh stratum+tcp://aleo-asia.f2pool.com:4400 accountname.workername
```

If the miner cannot be started successfully, use the following command.  `NONCE_TIMES` could be 12, 8, 4, 2, it depends on your device’s capacity. Higher `NONCE_TIMES` will bring better mining performance, but it requires more RAM, otherwise, the miner will report `out of memory` or other errors.

```
sh
export NONCE_TIMES=16 && nohup ./aleo-miner -u "stratum+tcp://aleo-asia.f2pool.com:4400" -w “accountname.workername“ -d 0 >> ./aleo-miner.log 2>&1 &
```

### parameter instruction

```
 -u, --url <URL>              Set the pool URL Format: <Working protocol>+<Wransport protocol>://<pool>:<port> Working protocol: stratum Transport protocols: tcp, ssl
 -w, --worker <WORKER>        Set the account && worker name [default: accountname.workername]
 -d, --devices <DEVICES>      -d 0 
 -g,                          -g 0
```

```
tail -f aleo-miner.log         print log
#显示log
pkill -9 aleo-miner            Kill mining progress
#结束挖矿进程
```