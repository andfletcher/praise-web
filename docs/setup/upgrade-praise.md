---
sidebar_position: 5
---

# How to upgrade Praise

The process of upgrading Praise to a new version is usually very straightforward. Most of the time the process consists of running the bundled upgrade script.

:::info

Always check the [release notes](https://github.com/commons-stack/praise/releases) before upgrading. At times you will be required to run the `setup.sh` script to upgrade environment variables.

:::

## Use ssh to access server

```
ssh root@xxx.xxx.xxx.xxx
```

## Run upgrade script

```
cd praise
sh upgrade.sh
```

## 👍 That's it

Your praise system should be upgraded!
