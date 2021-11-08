# Linux Experiments

Experiments with Linux.

## TCP/IP Sockets

See: `client.c`, `server.c`

Used to experiment with client and server.

1. Run client and server.
2. Connect
  
  ```
  tcp ESTAB 0 0 127.0.0.1:41350               127.0.0.1:commplex-link
  tcp ESTAB 0 0 127.0.0.1:commplex-link       127.0.0.1:41350
  ```
  
3. Send message via client to server.

  At this point we close the socket.
  Turns out that this does NOT actually close the socket handle itself.
  
  running `ss` shows that the sockets are still up.
  
  ```
  tcp FIN-WAIT-2 0 0 127.0.0.1:41374          127.0.0.1:commplex-link
  tcp CLOSE-WAIT 2 0 127.0.0.1:commplex-link  127.0.0.1:41374
  ```
