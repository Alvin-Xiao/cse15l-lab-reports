# Lab Report 3

[Home](index.md)

## SSH, GitHub Access, and SCP
*Alvin Xiao, April 28, 2022*

This report focuses on making remote running more convenient and efficient.

___

### Streamlining SSH Configuration

Rather than typing out the entirety of my course specific account, I can use an alias and type `ssh <alias>` instead. This is done through a configuration file in the `.ssh` folder that identifies the host and user, as shown below.

![config file](cse15l-lab3-p1.png)

We can confirm that this works by typing `ssh <alias>` (here I chose *ieng6* as an alias).

![ssh ieng6 command](cse15l-lab3-p2.png)

This alias also works with `scp` and copying files.

![scp ieng6 command](cse15l-lab3-p3.png)

### Setting up GitHub Access

The goal of this is to be able to commit and push changes from the ieng6 server. In order to do so, a public and private key must be used. The public key can be found (after it is added) on GitHub.

![public key](cse15l-lab3-p4.png)

The private key (and public key) can be found on the user's side.

![private key](cse15l-lab3-p5.png)

With this, files that are modified can be committed and pushed on the ieng6 server. The resulting commit can be found [here](https://github.com/Alvin-Xiao/markdown-parser/commit/94a49f3fecad9e0f54887995b46f7ad1e7ba846b).

![commit and push](cse15l-lab3-p6.png)

### Copying Whole Directories With SCP

The command `scp <file> <alias>` will only function for single files. In order to copy directories that contain more than one file, `scp` must be called recursively by using `-r`.

![scp -r command](cse15l-lab3-p6.png)

In the image above, all .java and .md files and the lib folder of the current directory will be copied over to the specified remote directory. 

![junit test](cse15l-lab3-p9.png)

The code was copied and works fine, as shown above. But these commands can be condensed into one line!

![scp -r one line](cse15l-lab3-p10.png)