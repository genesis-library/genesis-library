means: ```event-driven server-to-server API calls```

A common webhook example is, whenever a new commit is pushed to your Github repo, it triggers Github to make a call to your Jenkins server so it starts building the new code. Here we have a 'push-event driven Github-to-Jenkins API call'.

In this case Github will provide a JSON payload to Jenkins with all information about this new commit.