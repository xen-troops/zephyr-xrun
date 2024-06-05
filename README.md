# XRun

## OCI-compatible library with Xen support for Zephyr RTOS 

XRun is a library that provides a set of functions to start and manage containers in Zephyr RTOS. It is based on the OCI (Open Container Initiative) standard and supports Xen hypervisor.

## Building

To add the library to your Zephyr application, add the following to your `west.yml`:

```yaml
manifest:
  remotes:
    - name: xen-troops
      url-base: https://github.com/xen-troops

  projects:
    - name: zephyr-xrun
      remote: xen-troops
      revision: "main"
```

## Configuration

Minimal configuration required to use the library is to enable the following Kconfig options:

```Kconfig
CONFIG_XRUN=y
CONFIG_XRUN_SHELL_CMDS=y
```
For more information on the configuration options, please refer to the `Kconfig` file.

## Testing

To run the tests, execute the following command:

```bash
west build -b native_posix_64 -p always -t run
```
