# Command-Line Tricks

## Find and remove process listening on a port
`sudo lsof -nP -iTCP:$PORT | grep LISTEN`
`sudo kill -9 <PID>`