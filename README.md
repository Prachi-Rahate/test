just trials for git push and pull

problem with cloning: tried http, did not work to push repo (worked for pull), maybe because earlier i made it private now made public

tried ssh cloning:- in my git directory in laptop
1. Before generating new SSH keys, check if you already have existing SSH keys on your machine. In your terminal, navigate to the ~/.ssh/ directory and list the files:
   
> ls ~/.ssh/

If you see files named id_rsa and id_rsa.pub, you already have SSH keys. Skip to Step 3 to add the existing public key to your GitHub account.

3. Generate a New SSH Key:

If you don't have existing SSH keys or want to generate a new one, use the following command to generate a new SSH key pair:

> ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

Replace "your_email@example.com" with your email address associated with your GitHub account. Press Enter to accept the default file location and passphrase (or set a passphrase for added security). I did changed anything, just pressed enter twice

4. Add SSH Key to Your GitHub Account:

After generating the SSH key, you need to add the public key (id_rsa.pub) to your GitHub account or the Git hosting service you're using. Open the public key file with a text editor or use the following command to display the key:

> cat ~/.ssh/id_rsa.pub

- Click on "SSH and GPG keys" in the left sidebar on the github website

- Click "New SSH key" or "Add SSH key."

- Paste the copied public key into the "Key" field.

- Give the SSH key a descriptive title (e.g., "Personal Laptop").

- Click "Add SSH key" to save.


4.Update Remote URL to Use SSH:

To use SSH instead of HTTPS for remote Git operations, you need to update the remote URL of your repository. In your terminal, navigate to your local repository directory and use the following command to set the remote URL to the SSH method:

> git remote set-url origin git@github.com:username/repo.git

Replace username with your GitHub username and repo with the name of your repository.

5. Verify SSH Connection:
To verify that SSH is correctly set up, try to connect to GitHub using SSH:

> ssh -T git@github.com

You should see a message indicating that you've successfully authenticated, but you won't be able to use the shell. This is expected, as SSH is used for Git operations, not interactive sessions.

Now, you can use Git commands over SSH without being prompted for your credentials each time. SSH provides a secure and convenient way to interact with Git repositories, especially for users who prefer using SSH keys for authentication.

------------------------------------------------------------------------------------------------------------------------------

Another problem occured was during git push:

The error message you encountered after running git commit indicates that Git doesn't have enough information to identify the author of the commit. This happens when the required user information (name and email) is missing from the Git configuration. To resolve this issue, follow the steps below to set your Git identity:

Set Your User Information:
Open your terminal or command prompt and run the following commands, replacing the placeholders with your actual name and email address associated with your GitHub account:

> git config --global user.email "you@example.com"

> git config --global user.name "Your Name"

The --global flag sets this user information globally, meaning it will be applied to all repositories on your machine. If you prefer to set the identity only for the current repository, omit the --global flag.


Verify Git Identity:

To verify that your user information is correctly set, you can run the following commands:

> git config user.email

> git config user.name

These commands will display the email and name associated with your Git identity.

------------------------------------------------------------------------------------------------------------------------------------------------------------

To pull:-

> git pull

To push:-

- Check current branch

> git branch

- Add git command

> git add .

- Commit changes

> git commit -m "your changes"

this enlist the added files

4. push git
> git push

