# docker-php
Docker files for php environments
Use ```./php56.sh``` or ```./php70/sh``` to start an environment
The db-dump and code directories are shared.
The virtualhost.conf is shared because the apache instances should be equal.
Feel free to edit to your own flavour.

Quick note about those shell scripts: the directory change is necessary duo to .env files not be loaded otherwise.
