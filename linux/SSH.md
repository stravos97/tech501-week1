# SSH: Secure Shell

SSH (Secure Shell) is a protocol used to securely connect to remote systems over a network. It provides a secure channel over an unsecured network by encrypting the connection. SSH is commonly used for remote command-line login, file transfers, and secure tunneling.

## 2. Basic SSH Usage

### 2.1 Connecting to a Remote Server

- **Command**:
  ```bash
  ssh username@hostname_or_ip
  ```
  - `username`: The user account on the remote system.
  - `hostname_or_ip`: The remote system's hostname or IP address.

- **Example**:
  ```bash
  ssh user@example.com
  ```
  - Connects to the remote server `example.com` as the user `user`.

### 2.2 Specifying a Port

- **Command**:
  ```bash
  ssh -p port_number username@hostname_or_ip
  ```
  - `-p port_number`: Specifies a non-default SSH port (default is 22).

- **Example**:
  ```bash
  ssh -p 2222 user@example.com
  ```
  - Connects to `example.com` on port 2222.

### 2.3 Using SSH Keys for Authentication

- **Generate SSH Key Pair**:
  ```bash
  ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
  ```
  - `-t rsa`: Specifies the RSA key type.
  - `-b 4096`: Generates a 4096-bit key (more secure).
  - `-C "your_email@example.com"`: Adds a comment (usually your email) to the key.

- **Copy Public Key to Remote Server**:
  ```bash
  ssh-copy-id username@hostname_or_ip
  ```
  - Copies your public key to the remote server, allowing key-based authentication.

- **Example**:
  ```bash
  ssh-copy-id user@example.com
  ```
  - Copies your public key to `example.com` for the user `user`.

### 2.4 SSH Config File

- **Location**: `~/.ssh/config`
- **Purpose**: Simplifies SSH connections by storing configuration options.

- **Example Configuration**:
  ```plaintext
  Host example
      HostName example.com
      User user
      Port 2222
      IdentityFile ~/.ssh/id_rsa
  ```
  - Allows you to connect using `ssh example` instead of specifying the full command each time.
