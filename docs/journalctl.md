## Vacuum size
``` tab="Command"
journalctl --vacuum-size 5M
```

```bash tab="Output"
eleted archived journal /run/log/journal/7e98f39929ed41c59713feccf30f2e2f/system@036b736c778c4e51ae2db41381281698-000000000005071d-0005a7b23da341f8.journal (24.0M).
Deleted archived journal /run/log/journal/7e98f39929ed41c59713feccf30f2e2f/system@036b736c778c4e51ae2db41381281698-00000000000569d4-0005a7c47e87d6f8.journal (24.0M).
Deleted archived journal /run/log/journal/7e98f39929ed41c59713feccf30f2e2f/system@036b736c778c4e51ae2db41381281698-000000000005ccb4-0005a7d6d8d2c3a3.journal (24.0M).
Deleted archived journal /run/log/journal/7e98f39929ed41c59713feccf30f2e2f/system@036b736c778c4e51ae2db41381281698-0000000000062f5a-0005a7e7f95fa3c6.journal (24.0M).
Deleted archived journal /run/log/journal/7e98f39929ed41c59713feccf30f2e2f/system@036b736c778c4e51ae2db41381281698-00000000000691c3-0005a7fa5e0e466d.journal (24.0M).
Deleted archived journal /run/log/journal/7e98f39929ed41c59713feccf30f2e2f/system@036b736c778c4e51ae2db41381281698-000000000006f3fb-0005a80ccc91dcc7.journal (24.0M).
Deleted archived journal /run/log/journal/7e98f39929ed41c59713feccf30f2e2f/system@036b736c778c4e51ae2db41381281698-0000000000075694-0005a81f27d69d12.journal (24.0M).
Vacuuming done, freed 168.0M of archived journals on disk.
```
## Vacuum time
``` tab="Command"
journalctl --vacuum-time 7d
```

```bash tab="Output"
Deleted archived journal /run/log/journal/7e98f39929ed41c59713feccf30f2e2f/system@036b736c778c4e51ae2db41381281698-000000000003dfd9-0005a77b283964eb.journal (24.0M).
Deleted archived journal /run/log/journal/7e98f39929ed41c59713feccf30f2e2f/system@036b736c778c4e51ae2db41381281698-00000000000441dc-0005a78d84bc8d96.journal (24.0M).
Deleted archived journal /run/log/journal/7e98f39929ed41c59713feccf30f2e2f/system@036b736c778c4e51ae2db41381281698-000000000004a46d-0005a79fd8de6fac.journal (24.0M).
Vacuuming done, freed 72.0M of archived journals on disk.
```
