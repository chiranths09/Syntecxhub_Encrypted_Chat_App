Encrypted Chat Application
Overview

The Encrypted Terminal Chat Application is a secure client-server messaging system implemented using Python. The system demonstrates encrypted communication between multiple users through a centralized server.

Messages are encrypted on the client side using the Advanced Encryption Standard (AES) before being transmitted over the network. The server functions solely as a message relay and does not decrypt or access the content of the messages.

The application is designed to demonstrate basic principles of secure communication, encryption, and client-server architecture in a command-line environment.

Objectives

The primary objectives of this project are:

To implement secure communication using symmetric encryption

To demonstrate client-side message encryption and decryption

To build a multi-client chat system using socket programming

To simulate a secure messaging environment using a terminal interface

To illustrate basic cybersecurity concepts in application development

System Architecture

The system follows a client-server model.

Clients connect to a central server that routes encrypted messages between users.

Client A
   │
Encrypt Message (AES)
   │
   ▼
Server (Message Relay)
   │
   ▼
Client B
   │
Decrypt Message

The server does not decrypt messages and cannot read message content.

Features
Encrypted Messaging

All messages are encrypted using AES before being sent to the server. Only the receiving client decrypts the message.

Multi-Client Communication

Multiple clients can connect to the server simultaneously and exchange encrypted messages.

Client Selection

Users can switch between chat partners dynamically using command-based input.

Example command:

/switch username
Command-Based Interface

The application includes several built-in commands for interacting with the system.

Example commands include:

/switch username
/exit
/who
Message Logging

The server records connection events and message routing information in log files.

Error Handling

The application handles several runtime issues including:

client disconnection

invalid commands

network errors

Technologies Used

Programming Language:

Python

Networking:

TCP socket programming

Encryption:

AES symmetric encryption

Libraries:

PyCryptodome

Project Structure
EncryptedChatApp
│
├── server
│   ├── server.py
│   └── logger.py
│
├── client
│   ├── client.py
│   └── crypto_utils.py
│
└── logs
    └── chat_log.txt
server.py

Handles incoming client connections and routes encrypted messages between users.

logger.py

Records connection events and message routing information.

client.py

Implements the client interface, user commands, and communication with the server.

crypto_utils.py

Provides AES encryption and decryption functions used by the client.

Installation and Setup
1. Install Python

Ensure Python 3.8 or later is installed.

2. Install Required Library

Install the encryption library using pip.

pip install pycryptodome
3. Start the Server

Navigate to the server directory and run:

python server.py

The server will start listening for client connections.

4. Start a Client

Open a new terminal window and run:

python client.py

Enter a username when prompted.

Multiple clients can be started in separate terminals.

Example Usage

Client 1

Enter username: Alice
/switch Bob
Hello Bob

Client 2

Enter username: Bob
Alice: Hello Bob

Messages are transmitted in encrypted form and decrypted by the receiving client.

Encryption Process

When a user sends a message, the following process occurs:

Plain Text Message
      │
AES Encryption
      │
Encrypted Data
      │
Transmission via Server
      │
AES Decryption
      │
Original Message Displayed

This ensures that plaintext messages are not transmitted across the network.

Security Considerations

Although the system demonstrates encrypted communication, several security limitations should be noted.

Hardcoded Encryption Key

The encryption key is stored within the client application, which may allow extraction through reverse engineering.

Lack of Secure Key Exchange

The current implementation does not include a secure key exchange mechanism such as Diffie-Hellman or RSA.

No Transport Layer Security

The communication channel does not use TLS encryption, leaving the system potentially vulnerable to interception.

Client Authentication

The system does not implement authentication or identity verification for connected users.

Possible Improvements

Future versions of the system could include:

secure key exchange mechanisms

TLS encrypted communication

user authentication

graphical user interface

file transfer support

group chat functionality

message integrity verification

Educational Purpose

This project was developed to demonstrate core concepts in:

encrypted communication

socket programming

client-server networking

cybersecurity fundamentals

It provides a simplified environment for understanding how encryption can be applied to messaging systems.
