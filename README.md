# Java HTTP/HTTPS Proxy Server

## Features

- **HTTP/HTTPS Support**: Handles both HTTP and HTTPS requests seamlessly
- **Caching System**: 
  - Implements efficient caching of web pages and images
  - Reduces bandwidth usage and improves response times
  - Cached files are persisted between sessions
- **Website Blocking**:
  - Maintains a list of blocked websites
  - Blocked sites list persists between sessions
  - Easy to add or remove sites from the blocked list
- **Multi-threaded Architecture**:
  - Handles multiple client connections simultaneously
  - Each request is processed in its own thread
  - Efficient resource management
- **Timeout Management**: Implements connection timeouts to prevent hanging connections
- **File Type Support**: 
  - Handles various file types including HTML, images (PNG, JPG, JPEG, GIF)
  - Appropriate content-type handling for different file formats

## System Requirements

- Java Development Kit (JDK) 8 or higher
- Sufficient disk space for cache storage
- Network connectivity

## Installation

1. Clone this repository:
```bash
git clone https://github.com/yourusername/Proxy-Server.git
cd Proxy-Server
```

2. Compile the Java files:
```bash
javac Proxy.java RequestHandler.java
```

## Usage

1. Start the proxy server:
```bash
java Proxy
```
The server will start on port 8085 by default.

2. Configure your browser or application to use the proxy:
   - Proxy Address: localhost (or your machine's IP address)
   - Port: 8085

## Project Structure

- `Proxy.java`: Main proxy server implementation
  - Handles server initialization
  - Manages cached and blocked sites
  - Controls the server lifecycle
  
- `RequestHandler.java`: Request processing implementation
  - Handles individual client connections
  - Processes HTTP/HTTPS requests
  - Manages caching operations
  - Implements website blocking

## Cache Management

The proxy server maintains two persistent storage files:
- `cachedSites.txt`: Stores information about cached web pages and resources
- `blockedSites.txt`: Stores the list of blocked websites

Cached files are stored in the `cached/` directory with filenames derived from their URLs.

## Security Features

- HTTPS tunneling support for secure connections
- Timeout implementation to prevent denial-of-service attacks
- Website blocking capability for restricted access

## Limitations

- The proxy server uses a basic caching mechanism without cache invalidation
- HTTPS caching is not supported due to the encrypted nature of the protocol
- Website blocking is based on exact URL matches

## Contributing

Contributions are welcome! Please feel free to submit pull requests with improvements or bug fixes.

## License

This project is open source and available under the MIT License.

## Troubleshooting

1. **Connection Issues**
   - Verify the proxy server is running
   - Check if the port 8085 is available
   - Ensure proper network connectivity

2. **Performance Issues**
   - Check available disk space for cache
   - Monitor system memory usage
   - Consider clearing the cache if it grows too large

3. **Cache Problems**
   - Delete `cachedSites.txt` to reset the cache
   - Ensure write permissions in the cache directory
   - Check for disk space availability 
