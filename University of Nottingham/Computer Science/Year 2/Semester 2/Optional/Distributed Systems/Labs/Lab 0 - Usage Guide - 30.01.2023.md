Contents:
[[Distributed Systems]]

[Repository](https://projects.cs.nott.ac.uk/uon-repo/year-2/semester-2/distributed-systems/comp2014-2022-lab0)
[[Lab 0 setup.pdf]]
[[Lab Options.pdf]]


###### Old Instructions
	-   Check out the git repo for the lab
	-   In VSCode open the repo
	-   Then in VSCode command "Dev Containers: Reopen in Container" should come up to allow  waiting for container to build/start. (do this)
	-   In VSCode open a terminal - it should be in the container
		- You can check for this with a >< symbol in the bottom left of vscode
	-   Build using gradle, `gradle build`
	-   Run the server, `gradle run`
	-   Check that the server port e.g. 8000 has been forwarded


###### New Instructions
-   Open Docker
-   Check out the git repo for the lab
-   In VSCode open this folder
-   In VSCode open a terminal and cd into this folder
-   Type the following into the terminal
```
docker compose up
```
- On the left side of VSCode, click on the docker extension (whale)
	- ![[Pasted image 20230201145527.png]]
- Then right click the container which is running and attach shell
	- ![[Pasted image 20230201145704.png]]
- Your terminal should look like the following
	- ![[Pasted image 20230201150454.png]]
- And in the running container, build using gradle, `gradle build`
- And run the server, `gradle run`
- This is what your terminal should look like when the port has been accessed
	- ![[Pasted image 20230201150807.png]]
- Open the server URL in a browser, `http://localhost:8000/test` - it should say "This is the response"
	- ![[Pasted image 20230201150901.png]]
- Disconnect from the port by using ctrl + d (may take a moment)
- Then kill the container through docker (may take a moment)
	- ![[Pasted image 20230201151028.png]]
VSCode will reflect this momentarily:
	- ![[Pasted image 20230201151139.png]]
Finally, Close docker desktop by right clicking on it's icon on the taskbar
	- ![[Pasted image 20230201151529.png]]
