If you want to move the container to your other host, you can of course always package and export the container with the `machinectl` command.

```bash
# Export
machinectl export-tar Container1 ~/Container1.gz
# Import
machinectl import-tar ~/Container1.gz ContainerX
```

You can check the progress with `machinectl list-transfers` and cancel with `machinectl cancel-transfer` at any time during the import and export process.
