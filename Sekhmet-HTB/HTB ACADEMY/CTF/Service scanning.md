
Tools : Nmap


| Command                                       | Description                                                     |
| --------------------------------------------- | --------------------------------------------------------------- |
| `nmap 1.1.1.1`                                | Scan the first 1000k most commons ports                         |
| `nmpa -sC -sV -p- 1.1.1.1`                    | `sC` = more details `sV` = get version `-p-` scan all 65k ports |
| `nmap --script <script name> -p<port> <host>` | Script are located to /usr/share/nmap/script                    |
| `nmap -sV --script=banner -p21 10.10.10.0/24` | Get banner and version etc ...                                  |
