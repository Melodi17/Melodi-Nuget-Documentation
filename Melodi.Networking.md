## Melodi.Networking

### UDPConnection

**Overview:** A class for sending and receiving packets through the UDP protocol

```c#
UDPConnection udpConnection = new(1234);
udpConnection.onMessage = (ip, contentBytes, contentString) =>
{
    Console.WriteLine($"Message Recieved from {ip.Address}: {contentString}");
    udpConnection.Send("Hello back!");
};
udpConnection.Start();
```

### TCPConnectionServer

**Overview:** A simple TCP server

```c#
TCPConnectionServer server = new(1234);
server.onConnect = client =>
{
    Console.WriteLine("Device connected");
};
server.onDisconnect = client =>
{
    Console.WriteLine("Device disconnected");
};
server.onMessage = (client, contentString) =>
{
    Console.WriteLine($"Device {client.SocketId()} send a message: {contentString}");
    server.Send(client, "Hello back!");
};
server.Start();
```



 ### TCPConnectionClient

**Overview:** A simple TCP client

```c#
TCPConnectionClient client = new("localhost", 1234);
client.onConnect = () =>
{
    Console.WriteLine("Server connected");
};
client.onDisconnect = () =>
{
    Console.WriteLine("Server disconnected");
};
client.onMessage = contentString =>
{
    Console.WriteLine($"Server sent a message: {contentString}");
    client.Send("Hello back!");
};
client.Start();
```

