# ft_irc

## Overview
**ft_irc** is a group project developed as part of the 42 School curriculum. It is a custom implementation of an Internet Relay Chat (IRC) server, written in C++. The server adheres to the RFC 2812 specification, allowing users to connect via IRC clients such as **irssi** or **netcat**. The project includes support for various user and channel management features, as well as operator-specific modes.

## Features
- **Client Authentication**: Supports user nickname and username registration.
- **Channel Management**: Includes functionalities for creating, joining, and managing channels.
- **Private Messaging**: Allows users to send private messages to each other.
- **Operator Modes**: The following operator modes are implemented:
  - `+o`: Grant or revoke operator privileges.
  - `+i`: Set a channel to invite-only mode.
  - `+t`: Restrict topic changes to operators only.
  - `+k`: Protect a channel with a password.
  - `+l`: Limit the number of users in a channel.
- **Robust Networking**: Handles partial commands, unexpected client disconnections, and network disturbances without crashing.
- 
## Project Structure
The project is divided into three main components:
1. **Server**: Manages connections, message routing, and protocol handling.
2. **Channel**: Handles channel-specific logic, such as user lists, topic management, and operator modes.
3. **User**: Manages user data, including nicknames, authentication, and messaging.

## Usage
### Compilation
Use the provided Makefile to compile the project:
```bash
make
```
This will generate an executable named `ircserv`.

### Running the Server
Start the server with the following command:
```bash
./ircserv <port> <password>
```
- `<port>`: The port number for the server to listen on.
- `<password>`: The server password required for client connections.

### Connecting to the Server
Use an IRC client such as **irssi** or **netcat** to connect to the server:
- **irssi**:
  ```bash
  irssi -c <server_ip> -p <port> -w <password>
  ```
- **netcat**:
  ```bash
  nc <server_ip> <port>
  ```

## Testing
The server has been extensively tested using:
- Partial commands to ensure proper handling of incomplete inputs.
- Unexpected client disconnections to verify server stability.
- Flooding scenarios to check for resilience and performance.

## Collaboration
This project was completed as a **group effort**. Responsibilities were shared as follows:
- **Server Implementation**: Managed by my teammate.
- **Channel and User Logic**: Primarily my responsibility.
- **Overall Collaboration**: Both team members contributed to design discussions, testing, and debugging.
