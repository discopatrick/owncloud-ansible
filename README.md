# OwnCloud Ansible project

## TODO

* find a way of making the occ task idempotent. One way would be to first run `occ list` and see whether the command 'maintenance:install' was listed. If so, this would mean there had been no install yet, and we could proceed. If not, the install has already happened, and thus we should not run the task.

## Useful things to remember

* To open a shell as a specific user, you can do: `sudo -u www-data -s`