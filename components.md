# Steelmesh Components

Steelmesh is made up of a number of components:

## Bootloader (steelmesh-boot)

The steelmesh bootloader is responsible for the following operations:

- checking for an initial connection to CouchDB instances as specified in the config
- determining whether [redis] is available and should be used for IPC.
- initializating and starting the monitor process
- intercepting update notifications from the monitor and running `steelmesh-sync` as required.

## Application Update Monitor (steelmesh-monitor)

The application update monitor is used to monitor one or more CouchDB instances for changes (using the `_changes`) feed.

## Application Syncronizer (steelmesh-sync)

The application synchronizer is used to bring down application updates to the local machine from the remote CouchDB instance.  This can be done in response to application updates and also when the bootloader first starts.

[redis]: http://redis.io
