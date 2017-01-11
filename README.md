ansible-dashd
=========

This ansible role installs and configure a dashd server.  This role is setup to use a sudo user "ubuntu" as that is the default sudo user on new AWS instances.  Please modify the playbook accordingly for your own use.  This is essentially a modified version of https://github.com/challengerdeep/ansible-bitcoind - have to give credit where credit is due! :)

Requirements
------------

This role requires Ansible 1.4 higher and platforms listed in the metadata file.


Role Variables
--------------


Available options (and there default values) are:

    # Use dash testnet
    dashd_testnet: 0

    # Enable RPC server
    dashd_server: 1

    # connect through a proxy, replace by proxy IP when needed, eg: 127.0.0.1:9050
    dashd_proxy: False

	# switch mining on/off
    dashd_gen: 0

	# Maintain a full transaction index
    dashd_txindex: 0

	# Do not load the wallet and disable wallet RPC calls
    dashd_disablewallet: 0

    # Maximum number of inbound+outbound connections.
    dashd_maxconnections: 125

	### RPC Server options ###

	# RPC username, mandatory if server=1
	dashd_rpcuser:

	# RPC password, mandatory if server=1
	dashd_rpcpassword:

	# How many seconds dash will wait for a complete RPC HTTP request.
    dashd_rpctimeout: 30

    # By default, only RPC connections from localhost are allowed.  Specify
    # as many rpcallowip= settings as you like to allow connections from
    # other hosts (and you may use * as a wildcard character).
    # NOTE: opening up the RPC port to hosts outside your local
    # trusted network is NOT RECOMMENDED, because the rpcpassword
    # is transmitted over the network unencrypted.
    dashd_rpcallowip: [ "127.0.0.1", "192.168.1.*" ]

	# Listen for RPC connections on this TCP port. Uses default port if
	# not set
	dashd_rpcport:

Example Playbook
----------------

dashd.yml is included as an example.  Also, edit defaults/main.yml to configure the daemon, to make it suitable for your own use.


License
-------

MIT

Acknowledgements
----------------

Inspiration from: https://github.com/sivel/ansible-newrelic and https://github.com/challengerdeep/ansible-bitcoind
