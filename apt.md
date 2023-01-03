## Error

`Could not get lock /var/lib/dpkg/lock-frontend - open (11: Resource temporarily unavailable)`

[How to Fix ‘E: Could not get lock /var/lib/dpkg/lock’ Error in Ubuntu (phoenixnap.com)](https://phoenixnap.com/kb/fix-could-not-get-lock-error-ubuntu#:~:text=[Solution] Could not Get Lock Var Lib Dpkg,the command column%2C your system is... See More.)

```
ps aux | grep -i apt
ps aux | grep -i dpkg

kill -9 pid      (apt process)
```

