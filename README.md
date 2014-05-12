## Overcast Network Rotations

This repository contains a listing of files which correspond to all public [Overcast Network](https://oc.tc) rotations.

### Auto Deploy :zap:

Changes to these files *will* affect the rotations on production servers after a restart of the corresponding server.  As such, all map names must be valid, and the map must be present in the private Overcast Network maps repo.

### Contributing

Since this is a public repository, you are free to suggest changes to current rotations.  All that is needed is a pull-request.  The process for creating a pull-request is detailed as follows:

1. Fork the repo
2. Clone down the repo with `git clone https://github.com/<your-name>/Rotations.git`
3. Checkout a new branch `git checkout -b <name>`
4. Make changes by adding map names to the corresponding server file (seperated by a newline)
5. Commit your changes `git commit -am "<message>"`
6. Push your changes `git push`
7. Submit a pull-request on Github :octocat:

##### Alternative (Web based)
1. Go to the server file you want to edit the rotation of
2. Click Edit (This creates a fork of the repo, so you can edit it)
3. Make your changes
4. Give your PR a name, and click Propose File Change
5. In the description field, type what you have changed
6. Click Send Pull Request


During the review process, all that is needed for a deployment onto production servers is the consensus of the community, along with two map developers.  Once approved, your branch will be merged into master, and your changes will be reflected on restart.

Of note: during the build process for pull-requests, Travis-CI will validate all map names given in files.  If all maps are present, a :white_check_mark: will be displayed next to your branch. If not, a :x: will be displayed, and you will be responsible for fixing all invalid map names.
