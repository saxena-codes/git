# GIT and GITHUB using SSH

## Generating a new SSH key.

1. Open terminal and enter following commands to generate a new SSH key:

```
$ ssh-keygen -t ed25519 -C "your_email@example.com"
```

2. This creates a new SSH key, using the provided email as a label.

```
> Generating public/private ALGORITHM key pair.
```

3. When you're prompted to "Enter a file in which to save the key", you can press Enter to accept the default file location. Please note that if you created SSH keys previously, ssh-keygen may ask you to rewrite another key, in which case we recommend creating a custom-named SSH key. To do so, type the default file location and replace id_ALGORITHM with your custom key name.

```
> Enter a file in which to save the key (/home/YOU/.ssh/ALGORITHM):[Press enter]
```

4. At the prompt, type a secure passphrase.

```
> Enter passphrase (empty for no passphrase): [Type a passphrase]
> Enter same passphrase again: [Type passphrase again]
```

## Adding your SSH key to the SSH agent.

1. Before adding a new SSH key to the ssh-agent to manage your keys, you should have checked for existing SSH keys and generated a new SSH key.

2. Start the ssh-agent in the background.

```
$ eval "$(ssh-agent -s)"
> Agent pid 59566
```

3. Add your SSH private key to the ssh-agent.

```
ssh-add ~/.ssh/id_ed25519
```

> **Note**: If you created your key with a different name, or if you are adding an existing key that has a different name, replace id_ed25519 in the command with the name of your private key file.

## Adding the SSH public key to GitHub Account.

1. Copy the SSH public key to your clipboard.

```
$ cat ~/.ssh/id_ed25519.pub
# Then select and copy the contents of the id_ed25519.pub file
# displayed in the terminal to your clipboard
```

> After this, follow the link mentioned at `Reference 3` for adding the key to github account. 

## Git with SSH instead of https

1. Switching from https to ssh. Go to the repo directory and follow:

```
$ git remote -v
> origin  https://github.com/USERNAME/REPOSITORY.git (fetch)
> origin  https://github.com/USERNAME/REPOSITORY.git (push)
```

2. Change the remote.

```
$ git remote set-url origin git@github.com:USERNAME/REPOSITORY.git
```

3. Verify

```
$ git remote -v
> origin  git@github.com:USERNAME/REPOSITORY.git (fetch)
> origin  git@github.com:USERNAME/REPOSITORY.git (push)
``` 

## References:

1. <https://docs.github.com/en/authentication/connecting-to-github-with-ssh>

2. <https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent>

3. <https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account>

4. <https://gist.github.com/asksven/b37e8d83eca7f77484be9dd7af2b98e6>
