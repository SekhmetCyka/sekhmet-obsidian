
- Today, most web and mobile applications constantly interact with the internet.
- Most internet communications are conducted through web requests using the HTTP protocol.
- HTTP is an application-level protocol used to access resources on the World Wide Web.
- "Hypertext" refers to text with links to other resources that are easily interpretable by readers.
- HTTP communication involves a client-server model:
  - The client requests a resource from the server.
  - The server processes the request and returns the requested resource.
- The default port for HTTP communication is port 80, but it can be changed based on web server configuration.
- When using the internet, we often visit websites by entering a Fully Qualified Domain Name (FQDN) as a Uniform Resource Locator (URL), such as www.hackthebox.com.

Resources over HTTP are accessed via a `URL`, which offers many more specifications than simply specifying a website we want to visit. Let's look at the structure of a URL:

![[Pasted image 20240729044644.png]]


| **Component**  | **Example**          | **Description**                                                                                                                                                                       |
| -------------- | -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `Scheme`       | `http://` `https://` | This is used to identify the protocol being accessed by the client, and ends with a colon and a double slash (`://`)                                                                  |
| `User Info`    | `admin:password@`    | This is an optional component that contains the credentials (separated by a colon `:`) used to authenticate to the host, and is separated from the host with an at sign (`@`)         |
| `Host`         | `inlanefreight.com`  | The host signifies the resource location. This can be a hostname or an IP address                                                                                                     |
| `Port`         | `:80`                | The `Port` is separated from the `Host` by a colon (`:`). If no port is specified, `http` schemes default to port `80` and `https` default to port `443`                              |
| `Path`         | `/dashboard.php`     | This points to the resource being accessed, which can be a file or a folder. If there is no path specified, the server returns the default index (e.g. `index.html`).                 |
| `Query String` | `?login=true`        | The query string starts with a question mark (`?`), and consists of a parameter (e.g. `login`) and a value (e.g. `true`). Multiple parameters can be separated by an ampersand (`&`). |
| `Fragments`    | `#status`            | Fragments are processed by the browsers on the client-side to locate sections within the primary resource (e.g. a header or section on the page).                                     |

![[Pasted image 20240729045754.png]]


We can use cURL to get some file and others cheat
