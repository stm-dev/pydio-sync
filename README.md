pydio-sync
==========

New Python version of the Pydio synchronization client [work in progress]

This is a python rewrite of the current java-based synchro client. The work is still in progress and requires a couple of stuff to be deployed on the server-side to work. 

Server Setup
--
Pydio server needs the following to be turned on:
 * *RESTfull access* point (see /rest.php file) and a working pair of credentials for that (rest_user/rest_password)
 * *DB-based setup* : serial-based will soon be deprecated anyway
 * *Meta.syncable plugin* applied to the workspace you want to synchronize. This will track all the changes in a specific db-table, making it very quick for the sync client to load the last changes.
 * *php_rsync* extension on the server to allow transferring files deltas instead of complete files contents when modified. Not yet implemented but will be back at one point.

Client Setup
-- 
 * Make sure to install Python 2.7
 * Install Zero MQ on the client (see http://zeromq.org/area:download)
 * Install pip
 * Run: ```pip install git+https://github.com/pydio/pydio-sync.git```
 * Start main module with the following parameters: ```python -m pydio.main --server=http://yourserver --directory=/path/to/local/dir --workspace=workspace-alias --user=rest_user --password=rest_password```
