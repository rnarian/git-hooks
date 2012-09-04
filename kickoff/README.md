# Kickoff Hook 

---

Can be installed as a remote post-receive hook. 

Copy *post-receive.kickoffapp and config.kickoffapp* to `yourrepo.git/hooks`. Adjust config.kickoffapp.

Rename *post-receive.kickoffapp* to *post-receive* and make it executable `chmod +x yourrepo.git/hooks/post-receive`

---

## Using Kickoff hook with multiple repos

To use Kickoff hook with multiple repos copy *config.kickoffapp* to `yourrepo.git/hooks`. 

Move *post-receive.kickoffapp* to a folder which is accessible from all your repos.

Create new file *post-receive* in `yourrepo.git/hooks` with the following content:

    #!/bin/sh
    
    FILE=mktemp
    cat - > $FILE
    
    cat $FILE | /absolute/path/to/shared-git-hooks/post-receive.kickoffapp
    
    rm $FILE

And make it executable `chmod +x path/to/shared-git-hooks/post-receive`
