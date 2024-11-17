# Description

[Kallsyms_lookup_name](https://lwn.net/Articles/813350/) is not longer exported.
This Linux Kernel Module (LKM) implement the `kallsyms_lookup_name` function to retrieve the address of a specified kernel symbol.

# Features

* **Dynamic Symbol Lookup**: Retrieves the memory address of a specified kernel symbol (default: `sys_call_table`).
* **Kprobe Usage**: Uses a kernel probe (`kprobe`) to hook into the `kallsyms_lookup_name` function.
* **Module Parameter Support**: Accepts a configurable parameter to specify the desired kernel symbol name.

# Prerequisites

* **Kernel Configuration**: Ensure `CONFIG_KPROBES` is enabled in your kernel configuration.
* **Build Environment**: A working Linux kernel build environment (`make`, kernel headers, etc.).

# Build

```bash
make
```

# Usage

## Default

Default symbol is "sys_call_table" :

```bash
sudo insmod kallsyms_lookup_name.ko
```

## Custom

Custom symbol :

```bash
sudo insmod kallsyms_lookup_name.ko symbol_name=<symbol_to_lookup>
```
