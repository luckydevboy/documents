# Process

## Find and kill a process

Check active connections for a specific port:

```
netstat -ano | findstr :<PORT>
```

Kill a process:

```
taskkill /PID <PID> /F
```