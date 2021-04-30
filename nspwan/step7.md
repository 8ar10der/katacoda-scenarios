If you want to move the container to your other host, you can of course always package and export the container with the `machinectl` command.

* Export

`machinectl export-tar Container1 ~/Container1.gz`{{execute}}

* Import

`machinectl import-tar ~/Container1.gz ContainerX`{{execute}}


You can check the progress with `machinectl list-transfers`{{execute}} and cancel with `machinectl cancel-transfer`{{execute}} at any time during the import and export process.
