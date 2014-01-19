Tutorial and Walkthrough 
====================================

Refer to the github page on how to install the module `pybitsync <https://github.com/tiagomacarios/pybtsync>`_

Getting Started
---------------

.. note:: You dont need to have BitTorrent Sync running to follow this introduction.

To make things easier set you `BitTorrent sync API key <http://www.bittorrent.com/sync/developers>`_ to a environment variable. Using python only this can be done using:

::

	>>> import os
	>>> os.environ['PYBTSYNC_APIKEY'] = '****'

First thing you will need to import the module:

::

	>>> import pybtsync
	
After that you will need to start a BitTorrent Sync process to be able to communicate with it. This can be done by creating a :class:`BTSync_process` object. This will download the correct BitTorrent Sync for you OS and start it on the background.

::

	>>> btsync_process = pybtsync.BTSync_process()
	
.. note:: If you are using windows the line above will request for firewall access.

To get access to the API you will need to create a :class:`BTSync` object by using:

::

	>>> btsync = btsync_process.BTSync()

"Extracting" the :class:`BTSync` from the :class:`BTSync_process` object ensures that all the necessary credentials are correctly set on the background.

To check if everything is working correctly just try to get a listing of the folders:

::

 	>>> btsync.folders
	[]
	
Full set of commands on this getting started:

::

	import pybtsync
	btsync_process = pybtsync.BTSync_process()
	btsync = btsync_process.BTSync()