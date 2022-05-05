# Setting-up-SSH-key

#### Setting Up GitHub Authentication

In order for GitHub to deem our machines as "safe" to push code, we need to setup an identification key known as an `ssh key`.

Enter the following commands in your terminal, with your **_own_** information inserted:

```sh
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

The above email **_must_** be your GitHub email!

You should see the following prompt:

```sh
> Enter a file in which to save the key (/Users/you/.ssh/id_ed25519):
```

Leave it blank and hit <kbd>return</kbd> to save it in a default file.

You'll now be prompted to password protect the ssh key, but we can skip this portion. When prompted with the following, **hit** <kbd>return</kbd> **to leave the password as blank, both times**:

```sh
> Enter passphrase (empty for no passphrase):
> Enter same passphrase again:
```

Now, let's start the MacOS ssh-agent. Enter the following command into your terminal:

```sh
eval "$(ssh-agent -s)"
```

Now copy the ssh key to your clipboard with this command:

```sh
pbcopy < ~/.ssh/id_rsa.pub
```

To complete this setup, follow the instructions starting from Step 2 at this link **[HERE](https://docs.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account)**.

To check your installation, run:

```bash
ssh git@github.com
```

You should see output similar to:

```
Hi <you>! You've successfully authenticated, but GitHub does not provide shell access.
Connection to github.com closed.
```
